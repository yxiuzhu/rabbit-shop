<script setup lang="ts">
import { getHomeBannerAPI, getHomeCategoryAPI, getHomeHotAPI } from '@/services/home'
import type { BannerItem, CategoryItem, HotItem } from '@/types/home'

import { onLoad } from '@dcloudio/uni-app'
import { ref } from 'vue'

import CustomNavbar from './components/CustomNavbar.vue'

// 获取轮播图数据
const bannerList = ref<BannerItem[]>([])
const getHomeBannerData = async () => {
  const res = await getHomeBannerAPI()
  bannerList.value = res.result
}
// 小程序特有的钩子函数：onLoad 页面加载
onLoad(async () => {
  await Promise.all([getHomeBannerData()])
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
