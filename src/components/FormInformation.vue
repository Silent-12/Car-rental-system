<template>
  <div class="form-container">
    <!-- 姓名 -->
    <div class="form-item">
      <div class="info">姓名 :</div>
      <input type="text" maxlength="10" class="info-input" placeholder="请填写姓名" />
    </div>
    <!-- 学号 -->
    <div class="form-item">
      <div class="info">学号 :</div>
      <input type="text" maxlength="15" class="info-input" placeholder="请填写学号" />
    </div>
    <!-- 电话 -->
    <div class="form-item">
      <div class="info">电话 :</div>
      <input
        type="text"
        maxlength="11"
        class="info-input"
        placeholder="请填写电话,11位数~"
      />
    </div>
    <!-- 目的地 -->
    <div class="form-item">
      <div class="info">去哪 :</div>
      <input
        type="text"
        maxlength="10"
        class="info-input"
        placeholder="请填写你的目的地"
      />
    </div>
    <!-- 车辆数 -->
    <div class="form-item">
      <div class="info">数量 :</div>
      <input type="text" maxlength="2" class="info-input" placeholder="需要几辆车?" />
    </div>
    <!-- 租车时间 -->
    <div class="form-item">
      <div class="info">时间 :</div>
      <input type="text" maxlength="10" class="info-input" placeholder="什么时候出发?" />
    </div>
    <!-- 短租or日租 -->
    <div class="form-item">
      <div class="info">方式 :</div>
      <input type="text" maxlength="10" class="info-input" placeholder="短租or日租" />
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue"
</script>

<style lang="scss" scoped>
.form-container {
  width: 100%;
  height: 3rem;
  //   border: .01rem solid;
  padding: 15px;
  box-sizing: border-box;
  border-radius: 0.05rem;
  background: #fff;
  box-shadow: 0.1rem 0.1rem 0.08rem rgba(0, 0, 0, 0.05);
  font-size: 0.15rem;

  .form-item {
    width: 100%;
    height: 0.3rem;
    line-height: 0.3rem;
    display: flex;
    margin-bottom: 10px;

    .info {
      margin-right: 10px;
      min-width: 55px;
      font-weight: bold;
    }

    .info-input {
      width: 180px;
      border: 1px solid #e0e0e0;
      font-size: 15px;
      padding: 0 10px;
    }

    input[type="text"]:focus {
      outline: none;
    }
  }
}
</style>
