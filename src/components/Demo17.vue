<template>
  <div class="cart-box">
    <h3>购物车清单</h3>
    <div v-for="item in cart" :key="item.id" class="cart-item">
      <span class="name">{{ item.name }}</span>
      <span class="price">单价:¥{{ item.price }}</span>
      <div class="num-box">
        <button @click="changeNum(item,-1)">-</button>
        <span>{{ item.num }}</span>
        <button @click="changeNum(item,1)">+</button>
      </div>
      <span class="subtotal">小计:¥{{ item.price * item.num }}</span>
    </div>

    <div class="total-box">
      <p>商品总件数: {{ totalCount }} 件</p>
      <p>商品总价: <strong>¥{{ totalPrice }}</strong></p>
    </div>

    <div class="expensive-area">
      <h4>高价商品(单价>100)</h4>
      <div v-for="item in expensiveGoods" :key="item.id">
        {{ item.name }} ¥{{item.price}}
      </div>
    </div>
  </div>
</template>

<script setup>
import { reactive, computed } from 'vue';
const cart = reactive([
  { id: 1, name: "机械键盘", price: 299, num: 1 },
  { id: 2, name: "无线鼠标", price: 59, num: 2 },
  { id: 3, name: "4K显示器", price: 1299, num: 1 }
]);

// 修改数量，限制不能小于0
const changeNum = (item, step) => {
  item.num += step
  if(item.num < 0){
    item.num = 0
  }
}

// 计算总价
const totalPrice = computed(() => {
  let sum = 0;
  cart.forEach(item => {
    sum += item.price * item.num;
  });
  return sum;
})

// 计算总件数
const totalCount = computed(()=>{
  let count = 0
  cart.forEach(item=>{
    count += item.num
  })
  return count
})

// 过滤高价商品
const expensiveGoods = computed(()=>{
  return cart.filter(item=> item.price > 100)
})
</script>

<style scoped>
.cart-box { width: 620px; margin: 20px auto; padding:10px; }
.cart-item { display: flex; align-items: center; justify-content: space-between; padding: 10px; border-bottom: 1px solid #eee; }
.num-box button { width: 30px; height: 30px; cursor: pointer; }
.num-box span { display: inline-block; width: 40px; text-align: center; }
.total-box { margin-top: 20px; text-align: right; font-size: 18px; color: #f56c6c; }
.expensive-area { margin-top:30px;border:1px solid #eee;padding:10px; }
</style>