<template>
  <div class="header">
    <h2>{{ title }}</h2>
    <p>用户名：{{ userInfo.name }}</p>
    <p>用户ID：{{ userInfo.id }}</p>
    <p>标签列表：{{ tagList }}</p>
  </div>
</template>

<script setup>
defineProps({
  title:{
    type:String,
    required:true
  },
  userInfo:{
    type:Object,
    default: ()=>({name:"游客",id:0})
  },
  tagList:{
    type:Array,
    default: ()=>[]
  }
})
</script>

<style scoped>
</style>