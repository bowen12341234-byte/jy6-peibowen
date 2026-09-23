<template>
  <div class="box">
    <h2>v-if vs v-show对比实验</h2>
    <button @click="isShow = !isShow">切换显示隐藏</button>
    <div class="demo">
      <div v-if="isShow" class="item">👉 v-if控制模块</div>
      <div v-show="isShow" class="item">👉 v-show控制模块</div>
    </div>
  </div>
</template>

<script setup>
import {ref} from 'vue'
const isShow = ref(true)
</script>

<style scoped>
.box{width:500px;margin:30px auto;padding:20px;}
.item{margin:10px 0;padding:10px;border:1px solid #ccc;}
button{padding:6px 12px;cursor:pointer;}
</style>