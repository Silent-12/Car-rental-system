<template>
  <div class="Notice-container">{{ content }}</div>
</template>

<script setup>
import { ref, reactive } from "vue"

const props = defineProps({
  // 公告内容
  content: {
    type: String,
    default: "暂无公告内容 by：HLH",
  },
})
</script>

<style lang="scss" scoped>
.Notice-container {
  width: 100%;
  min-height: 0.4rem;
  padding: 0.1rem;
  box-sizing: border-box;
  font-size: 0.14rem;
  background: #ecf5ff;
  color: #3c9cff;
  border-radius: 0.05rem;
  box-shadow: 0.1rem 0.1rem 0.08rem rgba(0, 0, 0, 0.05);
  border: 0.05rem solid #fff;
}
</style>
