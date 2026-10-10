<template>
  <div class="goods-box">
    <button @click="isShow = !isShow">
      {{ isShow ? '隐藏列表' : '显示列表' }}
    </button>
    <!-- v-show控制整体列表显隐 -->
    <div v-show="isShow">
      <div v-for="item in goodsList" :key="item.id" class="goods-item">
        <div>
          <h4>{{ item.name }}</h4>
          <p>价格：{{ item.price }}元</p>
          <span v-if="item.price > 100" class="tag-high">高价商品</span>
          <span v-else class="tag-low">平价商品</span>
        </div>
        <button class="btn-del" @click="delGoods(item.id)">删除</button>
      </div>
      <!-- 列表为空兜底提示 -->
      <p v-if="goodsList.length === 0" class="empty-tip">暂无商品数据</p>
    </div>
  </div>
</template>

<script setup>
import { ref, reactive } from 'vue';
const isShow = ref(true);
const goodsList = reactive([
  { id: 101, name: "机械键盘", price: 89 },
  { id: 102, name: "4K显示器", price: 899 },
  { id: 103, name: "无线鼠标", price: 39 }
]);

// 根据id删除商品
const delGoods = (id) => {
  const index = goodsList.findIndex(item => item.id === id);
  if (index !== -1) {
    goodsList.splice(index, 1);
  }
};
</script>

<style scoped>
.goods-box { width: 500px; margin: 20px auto; }
button { padding: 8px 15px; cursor: pointer; margin-bottom: 10px; }
.goods-item { border: 1px solid #eee; padding: 10px; margin-bottom: 8px;
  border-radius: 4px; display: flex; align-items: center; justify-content: space-between; }
.tag-high { color: #fff; background: #f56c6c; padding: 2px 6px; border-radius: 3px; font-size: 12px; }
.tag-low { color: #67c23a; font-size: 12px; }
.btn-del { background: #909399; color: #fff; border: none; padding: 4px 10px; border-radius: 3px; cursor: pointer; }
.empty-tip { text-align: center; color: #999; padding: 20px; }
</style>