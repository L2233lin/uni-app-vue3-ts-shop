<script setup lang="ts">
import { useMemberStore } from '@/stores'
import { getHomeBannerAPI } from '@/services/home'

const memberStore = useMemberStore()
const getData = async () => {
  const res = await getHomeBannerAPI()
}
</script>

<template>
  <view class="my">
    <view>会员信息：{{ memberStore.profile }}</view>
    <button @tap="
      memberStore.setProfile({
        nickname: '黑马先锋',
      })
      " size="mini" plain type="primary">
      保存用户信息
    </button>
    <button @tap="memberStore.clearProfile()" size="mini" plain type="warn">清理用户信息</button>
    <button @tap="getData()" type="primary" size="mini" plain>获取信息</button>
  </view>
</template>

<style lang="scss">
//
</style>
