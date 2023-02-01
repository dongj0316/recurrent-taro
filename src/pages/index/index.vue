<template>
  <div class="tabs">
    <button @tap="index = 0">
      tab-0
    </button>

    <button @tap="index = 1">
      tab-1
    </button>
  </div>

  <div class="content">
    <BugUseReachBottom key="1" v-if="index === 0" :index="index">
      <div style="height: 1000px;">当前tab-0，请切好到tab-1后滚动到底部</div>
    </BugUseReachBottom>

    <BugUseReachBottom key="2" v-if="index === 1" :index="index">
      <div style="height: 1000px;">当前tab-1，请滚动到底部</div>
    </BugUseReachBottom>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import BugUseReachBottom from './BugUseReachBottom.vue'

const index = ref(0)
</script>

<style lang="scss">
.tabs {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  display: flex;
  align-items: center;

  > * {
    margin: 0;
  }
}

.content {
  padding-top: 200px;
}
</style>
