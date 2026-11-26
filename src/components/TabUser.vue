<template>
  <div class="tab-content">
    <h3>⚙ 用户设置页</h3>
    <input placeholder="设置页输入框" />
  </div>
</template>
<script setup>
import { onMounted, onUnmounted } from 'vue';
defineOptions({ name: 'TabUser' });

onMounted(() => console.log('[TabUser] 创建挂载 onMounted'));
onUnmounted(() => console.log('[TabUser] 销毁 onUnmounted'));
</script>
<style scoped>
.tab-content { padding: 15px; border: 1px solid #eee; }
</style>