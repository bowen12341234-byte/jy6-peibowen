<template>
    <Demo21 msg="你好" a="123" b="456"/>
    <Demo22 goods="京东" tag="666"/>
</template>

<script setup>
import Demo21 from '../components/Demo21.vue'
 const goods = {id:101,gname:"拯救者",price:8000,a:"123"}
 const tag = ['电脑','学习用具']
</script>