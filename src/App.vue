<script setup>
import HelloWorld from './components/HelloWorld.vue'
import Demo1 from './components/Demo1.vue'
import Demo2 from './components/Demo2.vue'
import Demo3 from './components/Demo3.vue'
import Demo4 from './components/Demo4.vue'
import Demo5 from './components/Demo5.vue'
import Demo6 from './components/Demo6.vue'
import Demo7 from './components/Demo7.vue'
import Demo06 from './components/Demo06.vue'
import Demo8 from './components/Demo8.vue'
import Demo9 from './components/Demo9.vue'
import Demo10 from './components/Demo10.vue'
import Demo11 from './components/Demo11.vue'
import Demo12 from './components/Demo12.vue'
import Demo13 from './components/Demo13.vue'
import Demo14 from './components/Demo14.vue'
import Demo15 from './components/Demo15.vue'
import Demo16 from './components/Demo16.vue'
import Demo17 from './components/Demo17.vue'
import Demo18 from './components/Demo18.vue'
import Demo19 from './components/Demo19.vue'
import Demo20 from './components/Demo20.vue'
import Demo21 from './views/Demo21.vue'
import D1 from './views/D1.vue'
import D2 from './views/D2.vue'
import D3 from './views/D3.vue'
</script>

<template>
  <D3/> 
</template>


<!--<template>
  <div class="app-container">
    <Header title="我的第一个商城" username="张三"/>
    <div class="main-content">页面主体</div>
    <Header title="底部备用导航" username="李四"/>
  </div>
</template>
<script setup>
import Header from './components/Header.vue'
</script>
<style scoped>
  .app-container{max-width:800px;margin:0 auto;}
  .main-content{padding:20px;text-align:center;}
</style>-->




<!--<template>
  <div class="app-container">
    <Header1 title="商城首页" :userInfo="u1" :taglist="tags"/>
    <!-- 不传对象数组，观察工厂函数生成默认值 
    <Header1 title="备用导航"/>
  </div>
</template> -->
<!--<script setup>
import Header1 from './components/Header1.vue'
const u1 = {name:"小明",id:1001}
const tags = ['VIP','新用户']
</script>

<style scoped>
.app-container{max-width:800px;margin:0 auto;}
</style>-->




<!--<template>
  <!-- 把原来的商城首页内容删掉，换成你的练习组件
  <Demo24 />
</template>

<script setup>
import Demo24 from './components/Demo24.vue';
</script>-->




<!--<template>
  <div id="app">
    <Header title="综合商城" username="小萌"/>
    <div class="goods-wrap">
      <h3>商品列表</h3>
      <GoodsCard
        v-for="item in goodsList"
        :key="item.id"
        :goods="item"
        :stock="item.stock"
        :isOnSale="item.isOnSale"
        @update-stock="handleUpdateStock"
      />
    </div>
    <div class="todo-wrap">
      <h3>待办事项</h3>
      <TodoItem v-for="t in todoList" :key="t.id" :todo="t" @delete-item="handleDelTodo"/>
    </div>
    <Footer />
  </div>
</template>

<script setup>
import {ref} from 'vue'
import Header from './components/Header.vue'
import GoodsCard from './components/GoodsCard.vue'
import TodoItem from './components/TodoItem.vue'

const goodsList = ref([
  {id:1,name:"无线鼠标",price:99,stock:30,isOnSale:true},
  {id:2,name:"机械键盘",price:299,stock:20,isOnSale:false}
])

const todoList = ref([{id:1,title:"复习组件化"}])

const handleUpdateStock = (payload)=>{
  const {goodsId,newStock} = payload
  const target = goodsList.value.find(g=>g.id === goodsId)
  if(target) target.stock = newStock
}

const handleDelTodo = (delId)=>{
  todoList.value = todoList.value.filter(i=>i.id!==delId)
}
</script>

<style scoped>
</style>-->




<!--<template>
  <div class="app">
    <h2>课时1：默认插槽与后备内容</h2>

    <MyCard>
      商品介绍
      <p>这是第一张卡片，父组件传入了文字。</p>
      <button @click="sayHi">点我（父组件的方法）</button>
    </MyCard>

    <MyCard>
      <template #title>商品介绍</template>
      <p>这是第二张卡片，使用了默认内容。</p>
      <button @click="sayHi">再点我（父组件的方法）</button>
    </MyCard>

    <MyCard>
      
    </MyCard>
  </div>
</template>

<script setup>
import MyCard from './components/MyCard.vue';

const sayHi = () => {
  alert('我是父组件 App.vue 里的方法，插槽内容可以使用父作用域的数据！');
};
</script>

<style scoped>
.app {
  max-width: 700px;
  margin: 30px auto;
}
</style>-->