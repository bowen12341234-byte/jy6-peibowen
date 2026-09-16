<template>
   <form action="/" method="post">
    <!-- 文本输入框 -->
    <label for="name">用户名：{{ name }}</label>
    <input type="text" v-model="name" id="name" name="name" required>

    <br>

    <!-- 单选按钮 -->
    <label>性别:{{ sex }}</label>
    <input type="radio" id="male" name="gender" v-model="sex" value="男" checked>
    <label for="male">男</label>
    <input type="radio" id="female" name="gender" v-model="sex" value="女">
    <label for="female">女</label>
   </form>
</template>

<script setup>
import { ref } from "vue";

  const name = ref('')
  const sex = ref('男')
</script>