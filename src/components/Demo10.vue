<template>
  <div class="box">
    <h2>v-if条件渲染练习</h2>
    <!-- 登录状态 -->
    <div v-if="isLogin">
      <p>👋欢迎尊贵用户！</p>
      <button @click="isLogin = false">退出登录</button>
    </div>
    <div v-else>
      <p>请登录后访问系统</p>
      <button @click="isLogin = true">点击登录</button>
    </div>

    <hr>
    <!-- 多分支判断成绩 -->
    <p>考试分数：<input v-model.number="score" placeholder="输入分数"></p>
    <div v-if="score >= 90">成绩等级：优秀</div>
    <div v-else-if="score >= 60">成绩等级：及格</div>
    <div v-else>成绩等级：不及格</div>
  </div>
</template>

<script setup>
import {ref} from 'vue'
const isLogin = ref(false)
const score = ref(0)
</script>

<style scoped>
.box{
  width:450px;
  margin:30px auto;
  padding:20px;
}
hr{margin:20px 0;}
input{padding:6px;width:200px;}
</style>，