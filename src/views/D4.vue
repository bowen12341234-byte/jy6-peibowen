<template>
    <h1>祖先组件</h1>
    <button @click="changeColor">切换颜色</button>
    <Day05/>
</template>
<script setup>
    import Day05 from '../components/Day05.vue';
    import { provide, ref } from 'vue';
    const color = ref('red')
    //传数据
    provide('color',color)
    const changeColor = ()=>{
        color.value = 'blue'
    }
    provide('newColor',changeColor)
</script>