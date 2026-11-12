<template>
  <Demo23 
    v-for="good in goods" 
    :key="good.id" 
    :goods="good" 
    @updateNum="handleUpdateNum"
    @removeGoods="handleRemove" 
  />
</template>

<script setup>
import { reactive } from 'vue';
import Demo23 from '../components/Demo23.vue';

const goods = reactive([
  { id: 101, gname: "拯救者", price: 8000, num: 2 },
  { id: 102, gname: "小新", price: 3000, num: 7 },
  { id: 103, gname: "天选", price: 5000, num: 5 },
  { id: 104, gname: "机械革命", price: 6000, num: 11 },
  { id: 105, gname: "外星人", price: 10000, num: 1 }
])

// 处理数量更新
const handleUpdateNum = (id, num) => {
  console.log(id + "***" + num);
  const item = goods.find(item => item.id === id);
  if (item) {
    item.num = Math.max(1, item.num + num);
  }
}

const handleRemove = (id) => {
  const index = goods.findIndex(item => item.id === id);
  if (index > -1) {
    goods.splice(index, 1); // 从数组中移除该项
  }
}
</script>