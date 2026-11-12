<template>
  <div class="card" :class="{sale: isOnSale}">
    <span v-if="isOnSale" class="tag">促销中</span>
    <h4>{{ goods.name }}</h4>
    <p>价格：￥{{ goods.price }}</p>
    <p>库存副本：{{ localStock }}</p>
    <button @click="localStock--">本地出库</button>
  </div>
</template>

<script setup>
   import { ref } from 'vue'
   const props = defineProps({
    goods:{
     type:Object,
     required:true,
     default: ()=>({})
    },
    stock:{
       type:Number,
       default:99
    },
    isOnSale:{
       type:Boolean,
       default:false
    }
})

const localStock = ref(props.stock)
</script>

<style scoped>
</style>