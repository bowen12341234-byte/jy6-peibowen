<template>
  <div class="item">
    <span>{{ todo.title }}</span>
    <button @click="handleDel">删除</button>
  </div>
</template>

<script setup>
defineProps({
  todo:{type:Object,required:true}
})
const emit = defineEmits(['delete-item'])
const handleDel = ()=>{
  const res = confirm("确定删除这条待办吗？")
  if(res){
    emit('delete-item', todo.id)
  }
}
</script>

<style scoped>
</style>