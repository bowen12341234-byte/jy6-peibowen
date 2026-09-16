<template>
    我叫XXX,今年{{age}},{{msg+1}}


    <!-- v-bind   : -->
    <img v-bind:src="url" alt="图片">
    <p :class="yd">好好学习</p>


    <!-- v-on  @ -->
    <button @click="oncli">点我啊</button>

</template>


<script setup>
const age = 20
const msg = age


import url1 from '../assets/hero.png'
const url =url1
const yd =  'a'


const oncli = ()=>{
    alert("点了一下")
}
</script>


<style scoped>
img{
    width: 100px;
    height: 100px;
}

.a{
    color: blue;
}
</style>