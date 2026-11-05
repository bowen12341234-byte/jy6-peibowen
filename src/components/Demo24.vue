<template>
  <Demo23 v-for="good in goods" :key="good.id" :goods="good" @updateNum="handleUpdateNum" />
</template>

<script setup>

import Demo13 from '../components/Demo13.vue';

const goods = [
  {id:101,gname:"拯救者",price:8000,num:2},
  {id:102,gname:"小新",price:3000,num:7},
  {id:103,gname:"天选",price:5000,num:5},
  {id:104,gname:"机械革命",price:6000,num:11},
  {id:105,gname:"外星人",price:10000,num:1}
]

//处理事件
const handleUpdateNum = (id,num)=>{
  console.log(id+"***"+num)
}
</script>