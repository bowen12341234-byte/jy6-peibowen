<template>
  {{ show() }}
  <button @click="num--">-</button>
  {{ num }}
  <button @click="num++">+</button>
</template>

<script setup>
import { onBeforeMount, onBeforeUpdate, onMounted, onUpdated } from 'vue';

/*const num = ref(1000)
onMounted(()=>{
  console.log("onMounted")
})
onBeforeMount(()=>{
  console.log("onBeforeMount")
})
const show = ()=>{
  console.log("aaaaaa")
}
onBeforeUpdate(()=>{
  console.log("onBeforeUpdate")
})*/

// 逻辑交互
//vue2写法
/* export default{
  data(){
    return{
      count: 43
    }
  }
}*/
//vue3写法
const count = 46

onBeforeUnmount(()=>{
  console.log("onBeforeUnmount")
})
onUnmounted(()=>{
  console.log("onUnmounted")
})
</script>