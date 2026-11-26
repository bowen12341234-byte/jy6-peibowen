<!-- src/components/TabHome.vue -->
<template>
  <div class="tab-content">
    <h3>📦 商品列表页</h3>
    <input v-model="keyword" placeholder="搜索商品（测试缓存保留）" />
    <p>数据加载时间：<b>{{ loadTime }}</b>（每次切回本页观察是否刷新）</p>
    <ul>
      <li v-for="g in goods" :key="g.id">{{ g.name }} - ¥{{ g.price }}</li>
    </ul>
  </div>
</template>
<script setup>
import { ref, onMounted, onActivated } from 'vue';
defineOptions({ name: 'TabHome' });

const keyword = ref('');
const loadTime = ref('');
const goods = ref([]);

// 模拟接口请求
const fetchGoods = () => {
  goods.value = [
    { id: 1, name: '无线鼠标', price: 99 },
    { id: 2, name: '机械键盘', price: 299 }
  ];
  loadTime.value = new Date().toLocaleTimeString();
};

// 首次进入：onMounted + onActivated 都会触发；之后每次切回只触发 onActivated
onMounted(() => console.log('[TabHome] 首次挂载'));
onActivated(() => {
  console.log('[TabHome] 激活，刷新数据');
  fetchGoods(); // 缓存页数据刷新策略：写在 onActivated，保证每次显示都是新数据
});
</script>
<style scoped>
.tab-content { padding: 15px; border: 1px solid #eee; }
</style>