<template>
  <div class="header1">
    <h2>{{ title }}</h2>
    <p>用户名：{{ userInfo.name }}</p>
    <p>用户ID：{{ userInfo.id }}</p>
    <p>标签列表：{{ taglist }}</p>
  </div>
</template>

<script setup>
defineProps({
  title: {
    type: String,
    required: true
  },
  userInfo: {
    type: Object,
    default: () => ({ name: "游客", id: 0 })
  },
  taglist: {
    type: Array,
    default: () => []
  }
})
</script>
<style scoped>
.header {height:80px;background:#42b983;color:#fff;display:flex;align-items:center;gap:20px;}
</style>