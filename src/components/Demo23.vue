<template>
  <p>
    {{ goods.id }} ---
    {{ goods.gname }} ---
    {{ goods.price }} ---
    <button @click="$emit('updateNum', goods.id, -1)">-</button>
    {{ goods.num }}
    <button @click="$emit('updateNum', goods.id, 1)">+</button>
    <button @click="$emit('removeGoods', goods.id)">删除</button>
  </p>
</template>

<script setup>
defineProps({
  goods: {
    type: Object,
    default: () => ({ id: 101, gname: "拯救者", price: 8000, num: 2 })
  }
})

// 注册事件（必须包含 removeGoods）
const emit = defineEmits(["updateNum", "removeGoods"])
</script>