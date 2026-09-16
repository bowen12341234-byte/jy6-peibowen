<template>
  <div class="box">
    <h2>实验1：单向绑定（:value）</h2>
    <p>在下面输入框打字，观察下方文字是否变化：</p>
    <input :value="msg1" placeholder="试试在这里打字" />
    <p>msg1的值：{{ msg1 }}</p>
    <p style="color:red;">→ 发现：输入框打字了，但msg1不变！</p>

    <hr />

    <h2>实验2：双向绑定（v-model）</h2>
    <p>在下面输入框打字，观察下方文字是否变化：</p>
    <input v-model="msg2" placeholder="试试在这里打字" />
    <p>msg2的值：{{ msg2 }}</p>
    <p style="color:green;">→ 发现：输入框打字，msg2实时同步！</p>

    <hr />

    <h2>实验3：手写v-model（:value + @input）</h2>
    <input :value="msg3" @input="msg3 = $event.target.value" placeholder="手写双向绑定" />
    <p>msg3的值：{{ msg3 }}</p>
    <p style="color:blue;">→ 发现：效果和v-model一模一样！</p>
  </div>
</template>

<script setup>
import { ref } from 'vue'
const msg1 = ref('初始值1')
const msg2 = ref('初始值2')
const msg3 = ref('初始值3')
</script>

<style scoped>

</style>