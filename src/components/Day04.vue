<template>
    <h1>孙子组件</h1>
    <div>
        <p :style="{color:color}">颜色{{ color }}</p>
        <button @click="changeColor">切换颜色</button>
    </div>
</template>

<script setup>
    import { inject } from 'vue';

    //从先祖获取数据
    const color = inject('color','green')
    const changeColor = inject('newColor',()=>{})
</script>