<template>
  <div class="toast" v-show="ifShow">
    <div>
      {{ message }}
    </div>
  </div>
</template>

<script setup>
import { ref, reactive } from "vue"

const message = ref("")
const ifShow = ref(false)

// 显示Toast
const show = (message = "默认文字", duration = 1000) => {
  ifShow = true
  message = message
  setTimeout(() => {
    ifShow = false
    message = ""
  }, duration)
}
</script>

<style lang="scss" scoped>
.toast {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  padding: 8px 10px;
  border-radius: 8px;
  z-index: 999;
  color: white;
  background-color: rgba(0, 0, 0, 0.5);
}
</style>
