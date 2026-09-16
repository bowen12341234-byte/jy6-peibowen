<template>
    {{ num }}
    <button @click="add">+1</button>
    <button @click="ad">-1</button>
    <button @click="reset">归零</button>
</template>

<script setup>
    /*let num = 0
    let add =()=>{
        num++
        console.log(num)
    }*/

import { ref } from "vue";


    //响应式
    const num = ref(0)
    const add =()=>{
        num.value++
        console.log(num.value)
    }

    //响应式
    const nu = ref(num)
    const ad =()=>{
        nu.value--
        console.log(nu.value)
    }

    const reset = () => {
    num.value = 0
    nu.value = 0
    console.log('已归零')
    }
</script>
<style scoped>


</style>