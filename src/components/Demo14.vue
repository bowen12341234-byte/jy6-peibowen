<template>
   <ul>
    <li v-for="good in newGoods" :key="good.id">
        {{ good.id }} &nbsp;&nbsp; {{ good.gname }} &nbsp;&nbsp; {{ good.price }}&nbsp;&nbsp;
        <button @click="good.num--">-</button>
         &nbsp;{{  good.num }} &nbsp;
        <button @click="good.num++">+</button>
    </li>
    总价： {{ total }}
   </ul>
  
</template>

<script setup>
import { computed,reactive,ref } from 'vue'

 //methods 普通方法
   /*  function a(){ alert(666) }
     var b = function(){ alert(777) }
     var c = ()=>{ alert(888) }

     var sum = (m,n)=>{
           return n*m 
     }
*/
     //computed 计算属性
     let a = ref(1)
     let b = ref(1)
     const d = computed(
        ()=>{
           alert(a.value+b.value) 
        }
     )

     //声明商品集合
     const goods = reactive([
        {id:1,gname:'瓜子',price:'100',num:10},
        {id:2,gname:'花生',price:'150',num:10},
        {id:3,gname:'糖',price:'50',num:2},
        {id:4,gname:'沙糖桔',price:'150',num:2},
        {id:5,gname:'甘蔗',price:'66',num:5},
        {id:6,gname:'饮料',price:'100',num:6},
        {id:7,gname:'猪蹄',price:'150',num:10}
     ])
    //计算总价
     const total = computed(
      ()=>{
         let sum = 0;
         goods.forEach(item=>{
           sum += item.price*item.num
         })
         return sum
      }
      
     )

     //500
     const newGoods = computed(
        ()=>{
          return goods.filter(item=>item.price>=5)
        }
     )
     
</script>

<style scoped>

</style>