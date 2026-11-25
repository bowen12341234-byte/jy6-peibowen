<!-- src/components/Child.vue（中间层依旧零处理） -->
<template>
  <div class="child-box">
    <p>中间层 Child：不做任何通信处理</p>
    <GrandSon />
  </div>
</template>
<script setup>
import GrandSon from './GrandSon.vue';
</script>
<style scoped>
.child-box {
  border: 1px solid #ccc;
  padding: 15px;
  margin: 10px 0;
}
</style>