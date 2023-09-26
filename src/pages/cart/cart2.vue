<!-- 为了在商品页面点击购物车时能够不出现tab栏 -->
<script setup lang="ts">
import CartMain from './components/CartMain.vue'
</script>

<template>
  <!-- 适配底部安全区 -->
  <CartMain safe-area-inset-bottom />
</template>
