<template>
  <Day03 :goodList="goodList">
    <template #default="{ item }">
      {{ item.id }}**{{ item.gname }}
    </template>
  </Day03>
</template>

<script setup>
import Day03 from '../components/Day03.vue';
import { reactive } from 'vue';

// 商品列表
const goodList = reactive([
  { id: 100, gname: "哇哈哈", price: 1.2 },
  { id: 200, gname: "康师傅", price: 2 },
  { id: 300, gname: "百岁山", price: 3 }
])
</script>