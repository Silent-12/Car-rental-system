<template>
  <div class="app-container">
    <!-- 标题 -->
    <WebHead title="信科校园租车"></WebHead>

    <!-- 公告栏 -->
    <div style="padding: 10px">
      <NoticeBoard></NoticeBoard>
    </div>

    <!-- 内容 -->
    <div style="padding: 10px">
      <FormInformation></FormInformation>
    </div>
  </div>
</template>

<script setup>
import WebHead from "./components/WebHead.vue"
import NoticeBoard from "./components/NoticeBoard.vue"
import FormInformation from "./components/FormInformation.vue"
</script>

<style lang="scss" scoped>
.app-container {
  width: 100%;
  box-sizing: border-box;
}
</style>
