<template>
  <div class="web-contaienr">
    {{ title }}
  </div>
</template>

<script setup>
const props = defineProps({
  // 标题
  title: {
    type: String,
    default: "标题",
  },
})
</script>

<style lang="scss" scoped>
.web-contaienr {
  width: 100%;
  height: 0.45rem;
  background: #0f5bff;
  text-align: center;
  line-height: 0.45rem;
  color: #fff;
}
</style>
