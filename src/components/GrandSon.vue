<!-- src/components/GrandSon.vue -->
<template>
  <div class="grandson" :style="{ color: theme.color }">
    <p>当前主题色：{{ theme.color }}，当前字号：{{ theme.fontSize }}</p>
    <!-- 合规修改：调用祖先提供的函数，而不是直接 theme.color = xxx -->
    <button @click="updateTheme({ color: '#f56c6c' })">后代一键切红色</button>
    <button @click="resetTheme">恢复默认</button>
  </div>
</template>
<script setup>
import { inject } from 'vue';

// ✅ 保持对象引用，禁止解构（解构会丢失响应式！）
const theme = inject('app-theme', { color: '#333', fontSize: '14px' });
const updateTheme = inject('app-updateTheme', () => {});

const resetTheme = inject('app-resetTheme', () => {});
</script>
<style scoped>
.grandson {
  padding: 10px;
  background: #f7f7f7;
}
button {
  margin-right: 8px;
}
</style>