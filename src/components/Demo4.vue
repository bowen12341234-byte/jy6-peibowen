<template>
    {{ msg }}
    <input type="text" v-model="msg"/>

</template>

<script setup>
    import { ref } from 'vue';
    const msg = ref("hello")

</script>

<style scoped>

</style>