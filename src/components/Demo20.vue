<template>
    <div>

    </div>
</template>
<script setup>
import{ref,computed,watch} from 'vue'
const msg = ref("")
const list = ([
    {id:1,name:"苹果"},
    {id:2,name:"香蕉"},
    {id:3,name:"橙子"}
    ])
const filterList = computed(() => {

  if (msg.value.trim() === '') {
    return list
  }
  return list.filter(item => item.name.includes(msg.value))
})
watch(msg, (newVal, oldVal) => {
  console.log('最新输入的值:', newVal)
})
</script>
<style scoped>

</style>