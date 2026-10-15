<template>
  <div class="box">
    <h2>computed vs methods 缓存对比</h2>
    <p>原始数字：<input v-model.number="num" /></p>

    <h3>methods调用（写括号）</h3>
    <p>{{ getDouble() }}</p>
    <p>{{ getDouble() }}</p>

    <h3>computed调用（不加括号）</h3>
    <p>{{ doubleNum }}</p>
    <p>{{ doubleNum }}</p>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'
const num = ref(5)

// 普通方法 methods
const getDouble = () => {
  console.log("methods执行")
  return num.value * 2
}

// 计算属性 computed
const doubleNum = computed(() => {
  console.log("computed执行")
  return num.value * 2
})
</script>

<style scoped>

</style>