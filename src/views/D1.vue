<template>
  <h1>父组件</h1>
  <Day01>
    <h1>标题</h1>
    <button @click="say">按钮</button>
  </Day01>
------------------------------------------
  <Day01>
    <template v-slot:zheshi>
      <h1>标题</h1>
      <button @click="say">按钮</button>
    </template>
  </Day01>

</template>

<script setup>
import Day01 from '../components/Day01.vue';
const say = () =>{
    alert('按钮被点击了')
}
</script>