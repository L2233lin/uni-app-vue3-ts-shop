<script setup lang="ts">
import { OrderState } from '@/utils/constants'
import { orderStateList } from '@/utils/constants'
import {
  deleteMemberOrderAPI,
  getMemberOrderAPI,
  putMemberOrderReceiptByIdAPI,
} from '@/services/order'
import type { OrderItem } from '@/types/order'
import type { OrderListParams } from '@/types/order'
import { onMounted, ref } from 'vue'
import { getPayMockAPI, getPayWxPayMiniPayAPI } from '@/services/pay'

// 获取屏幕边界到安全区域距离
const { safeAreaInsets } = uni.getSystemInfoSync()

// 定义 porps
const props = defineProps<{
  orderState: number
}>()

// 请求参数
const queryParams: Required<OrderListParams> = {
  page: 1,
  pageSize: 5,
  orderState: props.orderState,
}

// 获取订单列表
const orderList = ref<OrderItem[]>([])
// 是否加载中标记，用于防止滚动触底触发多次请求
const isLoading = ref(false)
const getMemberOrderData = async () => {
  // 如果数据出于加载中，退出函数
  if (isLoading.value) return
  // 退出分页判断
  if (isFinish.value === true) {
    return uni.showToast({ icon: 'none', title: '没有更多数据~' })
  }
  // 发送请求前，标记为加载中
  isLoading.value = true
  // 发送请求
  const res = await getMemberOrderAPI(queryParams)
  orderList.value = res.result.items
  // 发送请求后，重置标记
  isLoading.value = false
  // 数组追加
  orderList.value.push(...res.result.items)
  // 分页条件
  if (queryParams.page < res.result.pages) {
    // 页码累加
    queryParams.page++
  } else {
    // 分页已结束
    isFinish.value = true
  }
}

onMounted(() => {
  getMemberOrderData()
})

// 订单支付
const onOrderPay = async (id: string) => {
  // 通过环境变量区分开发环境
  if (import.meta.env.DEV) {
    // 开发环境：模拟支付，修改订单状态为已支付
    await getPayMockAPI({ orderId: id })
  } else {
    // 生产环境：获取支付参数 + 发起微信支付
    const res = await getPayWxPayMiniPayAPI({ orderId: id })
    await wx.requestPayment(res.result)
  }
  // 成功提示
  uni.showToast({ title: '支付成功' })
  // 更新订单状态
  const order = orderList.value.find((v) => v.id === id)
  order!.orderState = OrderState.DaiFaHuo
}

// 确认收货
const onOrderConfirm = (id: string) => {
  // 二次确认弹窗
  uni.showModal({
    content: '为保障您的权益，请收到货并确认无误后，再确认收货',
    success: async (success) => {
      if (success.confirm) {
        const res = await putMemberOrderReceiptByIdAPI(id)
        // 确认成功，更新为待评价
        const order = orderList.value.find((v) => v.id === id)
        order!.orderState = OrderState.DaiPingJia
      }
    },
  })
}

// 删除订单
const onOrderDelete = (id: string) => {
  // 二次确认
  uni.showModal({
    content: '是否删除订单',
    success: async (success) => {
      if (success.confirm) {
        await deleteMemberOrderAPI({ ids: [id] })
        // 删除成功，界面中删除订单
        const index = orderList.value.findIndex((v) => v.id === id)
        orderList.value.splice(index, 1)
      }
    },
  })
}

// 是否分页结束
const isFinish = ref(false)
// 是否触发下拉刷新
const isTriggered = ref(false)
// 自定义下拉刷新被触发
const onRefresherrefresh = async () => {
  // 开始动画
  isTriggered.value = true
  // 重置数据
  queryParams.page = 1
  orderList.value = []
  isFinish.value = false
  // 加载数据
  await getMemberOrderData()
  // 关闭动画
  isTriggered.value = false
}
</script>
<template>
  <scroll-view
    refresher-enabled
    @refresherrefresh="onRefresherrefresh"
    :refresher-triggered="isTriggered"
    @scrolltolower="getMemberOrderData"
    scroll-y
    class="orders"
  >
    <view class="card" v-for="order in orderList" :key="order.id">
      <!-- 订单信息 -->
      <view class="status">
        <text class="date">{{ order.createTime }}</text>
        <!-- 订单状态文字 -->
        <text>{{ orderStateList[order.orderState].text }}</text>
        <!-- 待评价/已完成/已取消 状态: 展示删除订单 -->
        <text
          v-if="order.orderState >= OrderState.DaiPingJia"
          class="icon-delete"
          @tap="onOrderDelete(order.id)"
        ></text>
      </view>
      <!-- 商品信息，点击商品跳转到订单详情，不是商品详情 -->
      <navigator
        v-for="item in order.skus"
        :key="item.id"
        class="goods"
        :url="`/pagesOrder/detail/detail?id=${order.id}`"
        hover-class="none"
      >
        <view class="cover">
          <image mode="aspectFit" :src="item.image"> </image>
        </view>
        <view class="meta">
          <view class="name ellipsis">{{ item.name }}</view>
          <view class="type">{{ item.attrsText }}</view>
        </view>
      </navigator>
      <!-- 支付信息 -->
      <view class="payment">
        <text class="quantity">共{{ order.totalNum }}件商品</text>
        <text>实付</text>
        <text class="amount"> <text class="symbol">¥</text>{{ order.payMoney }}</text>
      </view>
      <!-- 订单操作按钮 -->
      <view class="action">
        <!-- 待付款状态：显示去支付按钮 -->
        <template v-if="order.orderState === OrderState.DaiFuKuan">
          <view class="button primary" @tap="onOrderPay(order.id)">去支付</view>
        </template>
        <template v-else>
          <navigator
            class="button secondary"
            :url="`/pagesOrder/create/create?orderId=${order.id}`"
            hover-class="none"
          >
            再次购买
          </navigator>
          <!-- 待收货状态: 展示确认收货 -->
          <view
            v-if="order.orderState === OrderState.DaiShouHuo"
            class="button primary"
            @tap="onOrderConfirm(order.id)"
            >确认收货</view
          >
        </template>
      </view>
    </view>
    <!-- 底部提示文字 -->
    <view class="loading-text" :style="{ paddingBottom: safeAreaInsets?.bottom + 'px' }">
      {{ isFinish ? '没有更多数据~' : '正在加载...' }}
    </view>
  </scroll-view>
</template>
