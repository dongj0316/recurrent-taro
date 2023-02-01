<template>
  <slot></slot>
</template>

<script setup>
import { onUnmounted } from 'vue'
import { useReachBottom } from '@tarojs/taro'

const props = defineProps({
  index: String,
})

let destroyed = false
onUnmounted(() => {
  destroyed = true
})

useReachBottom(() => {
  if (destroyed) {
    console.log(`tab-${props.index}`, 'BUG: 组件已销毁')
  }
})
</script>
