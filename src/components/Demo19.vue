<template>
  <div class="search-box">
    <p class="tip">当前搜索词：{{ keyword || '暂无' }}</p>
    <input v-model="keyword" placeholder="输入关键词搜索..." />

    <ul v-if="filterList.length > 0">
      <li v-for="item in filterList" :key="item.id">{{ item.name }}</li>
    </ul>
    <p v-else class="empty">暂无匹配数据</p>
  </div>
</template>

<script setup>
import { ref, watch, computed, onMounted } from 'vue';
const keyword = ref('');
const allList = ref([]);

// 页面加载完成，模拟接口获取全部数据
onMounted(() => {
  console.log('页面加载完毕，开始请求数据...');
  setTimeout(() => {
    // ref数组整体替换，必须加.value
    allList.value = [
      { id: 1, name: "Vue3 基础教程" },
      { id: 2, name: "JavaScript 核心" },
      { id: 3, name: "CSS3 动画入门" }
    ]
  }, 500);
});

// watch监听搜索词变化，做副作用（打印，真实业务发搜索请求）
watch(keyword, (newVal, oldVal) => {
  console.log(`搜索词变化：从 "${oldVal}" 变为 "${newVal}"`);
});

// 同步派生过滤列表，使用computed，不要用watch手动改数组
const filterList = computed(() => {
  if (!keyword.value) return allList.value;
  return allList.value.filter(item => item.name.includes(keyword.value))
})
</script>

<style scoped>
.search-box {
  width: 400px;
  margin: 30px auto;
}
input {
  width: 100%;
  padding: 8px;
  box-sizing: border-box;
}
.tip {
  color: #999;
  font-size: 12px;
}
ul {
  list-style: none;
  padding: 0;
}
li {
  padding: 8px;
  border-bottom: 1px solid #eee;
}
.empty {
  color: #ccc;
  text-align: center;
  padding: 20px;
}
</style>