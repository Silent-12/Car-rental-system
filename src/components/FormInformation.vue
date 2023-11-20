<template>
  <div class="form-container">
    <!-- 姓名 -->
    <div class="form-item">
      <div class="info">姓名 :</div>
      <input
        type="text"
        maxlength="10"
        class="info-input"
        placeholder="请填写姓名"
        v-model="info.name"
      />
    </div>
    <!-- 学号 -->
    <div class="form-item">
      <div class="info">学号 :</div>
      <input
        type="number"
        maxlength="15"
        class="info-input"
        placeholder="请填写学号"
        v-model="info.stutID"
      />
    </div>
    <!-- 电话 -->
    <div class="form-item">
      <div class="info">电话 :</div>
      <input
        type="number"
        maxlength="11"
        class="info-input"
        placeholder="请填写电话,11位数~"
        v-model="info.phone"
      />
    </div>
    <!-- 目的地 -->
    <div class="form-item">
      <div class="info">去哪 :</div>
      <input
        type="text"
        class="info-input"
        placeholder="请填写你的目的地"
        v-model="info.end"
      />
    </div>
    <!-- 车辆数 -->
    <div class="form-item">
      <div class="info">数量 :</div>
      <input
        type="number"
        maxlength="2"
        class="info-input"
        placeholder="需要几辆车?"
        v-model="info.carNum"
      />
    </div>
    <!-- 租车时间 -->
    <div class="form-item">
      <div class="info">时间 :</div>
      <input
        type="datetime-local"
        class="info-input"
        placeholder="什么时候出发?"
        v-model="info.dateTime"
      />
    </div>
    <!-- 短租or日租 -->
    <div class="form-item">
      <div class="info">方式 :</div>
      <select name="fruit" :onchange="changeMode">
        <option value="1" selected>短租</option>
        <option value="2">日租</option>
      </select>
    </div>

    <div class="btn" @click="throttle()">提交</div>
  </div>
</template>

<script setup>
import { getCurrentInstance, reactive, ref } from "vue"

// 数据初始化
const info = reactive({
  name: "",
  stutID: "",
  phone: "",
  end: "",
  carNum: 1,
  dateTime: "",
  mode: "1",
})

let timer = ref(null)

// 按钮节流
const throttle = () => {
  if (timer) {
    clearTimeout(timer)
  }
  timer = setTimeout(() => {
    checkForm()
  }, 300)
}

// 检查表单数据是否符合规范
const checkForm = () => {
  console.log(info)

  if (!info.name || !info.end || !info.carNum || !info.dateTime) {
    return
  }

  // 单独校验学号和电话,因为默认是int类型
  if (info.stutID.length !== 10 || info.phone.length !== 11) {
    return
  }
}

// slect选择回调
const changeMode = (e) => {
  info.mode = e.target.value
}
</script>

<style lang="scss" scoped>
.form-container {
  width: 100%;
  //   height: 3rem;
  //   border: .01rem solid;
  padding: 0.15rem;
  box-sizing: border-box;
  border-radius: 0.05rem;
  background: #fff;
  box-shadow: 0.1rem 0.1rem 0.08rem rgba(0, 0, 0, 0.05);
  font-size: 0.15rem;

  .btn {
    width: 1.5rem;
    height: 0.4rem;
    color: #fff;
    background: #0f5bff;
    line-height: 0.4rem;
    text-align: center;
    border-radius: 0.05rem;
    margin: 0 auto;
    margin-top: 0.3rem;
  }

  .form-item {
    width: 100%;
    height: 0.3rem;
    line-height: 0.3rem;
    display: flex;
    margin-bottom: 0.1rem;

    .info {
      margin-right: 0.1rem;
      min-width: 0.55rem;
      font-weight: bold;
    }

    .info-input {
      width: 2rem;
      border: 0.01rem solid #e0e0e0;
      font-size: 0.15rem;
      padding: 0 0.1rem;
    }

    input:focus {
      outline: none;
    }

    select {
      appearance: none；;
    }
  }
}
</style>
