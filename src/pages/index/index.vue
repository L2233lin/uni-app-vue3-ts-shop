<script setup lang="ts">
import type { BannerItem } from '@/types/home';
import CustomNavbar from './components/CustomNavbar.vue'
import { ref } from 'vue';
import { getHomeBannerAPI } from '@/services/home';
import { onLoad } from '@dcloudio/uni-app';

// 获取轮播图数据
const bannerList = ref<BannerItem[]>([])
const getHomeBannerData = async () => {
  const res = await getHomeBannerAPI()
  bannerList.value = res.result
}

// 页面加载
onLoad(() => {
  getHomeBannerData()
})
</script>

<template>
  <!-- 自定义导航栏 -->
  <CustomNavbar />
  <!-- 自定义轮播图 -->
  <XtxSwiper :list="bannerList" />
</template>

<style lang="scss">
//
</style>
