<template>
  <div class="header">
    <h2>{{ title }}</h2>
    <p>当前用户：{{ username }}</p>
  </div>
</template>
<script setup>
defineProps({
  title: String,
  username: String
})
</script>
<style scoped>
  .header {
    height: 80px;
    background: #42b983;
    color: #fff;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding:0 20px;
  }
</style>