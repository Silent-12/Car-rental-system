<template>
  <div class="app-container">
    <!-- 标题 -->
    <WebHead title="信科校园租车"></WebHead>

    <!-- 公告栏 -->
    <div style="padding: 10px">
      <NoticeBoard></NoticeBoard>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue"
import WebHead from "./components/WebHead.vue"
import NoticeBoard from "./components/NoticeBoard.vue"
</script>

<style lang="scss" scoped>
.app-container {
  width: 100%;
}
</style>
