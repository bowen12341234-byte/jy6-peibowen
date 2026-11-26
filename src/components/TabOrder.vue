<template>
  <div class="tab-content">
    <h3>📋 订单管理页</h3>
    <input placeholder="订单页输入框" />
  </div>
</template>
<script setup>
import { onMounted, onUnmounted } from 'vue';
defineOptions({ name: 'TabOrder' });

onMounted(() => console.log('[TabOrder] 创建挂载 onMounted'));
onUnmounted(() => console.log('[TabOrder] 销毁 onUnmounted'));
</script>
<style scoped>
.tab-content { padding: 15px; border: 1px solid #eee; }
</style>