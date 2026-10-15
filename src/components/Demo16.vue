<template>
  <div class="box">
    <h2>computed数组过滤练习</h2>
    <p>最低价格筛选：<input v-model.number="minPrice" /></p>

    <h4>全部商品</h4>
    <div v-for="item in goods" :key="item.id">{{item.name}} ${{item.price}}</div>

    <h4>筛选后商品（价格大于输入值）</h4>
    <div v-for="item in filterGoods" :key="item.id">{{item.name}} ${{item.price}}</div>
  </div>
</template>

<script setup>
import {reactive,ref,computed} from 'vue'
const minPrice = ref(100)
const goods = reactive([
  {id:1,name:"机械键盘",price:299},
  {id:2,name:"无线鼠标",price:59},
  {id:3,name:"4K显示器",price:1299},
  {id:4,name:"耳机",price:199}
])

const filterGoods = computed(()=>{
  console.log("过滤执行了")
  return goods.filter(item=> item.price >= minPrice.value)
})
</script>

<style scoped>
.box{width:500px;margin:30px auto;padding:20px;}
input{padding:6px;width:200px;}
</style>