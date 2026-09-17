<template>
  <div class="form-box">
    <h3>用户注册表单</h3>

    <!-- 1. 文本输入框 -->
    <p>
      <label class="label">用户名：</label>
      <input type="text" v-model="user.username" placeholder="请输入用户名" />
    </p>

    <!-- 2. 多行文本框 -->
    <p>
      <label class="label">个人简介：</label><br />
      <textarea v-model="user.intro" rows="3" placeholder="介绍一下自己吧"></textarea>
    </p>

    <!-- 3. 单选框：共用 user.gender，通过 value 区分 -->
    <p>
      <label class="label">性别：</label>
      <input type="radio" v-model="user.gender" value="男" id="man" />
      <label for="man">男</label>
      <input type="radio" v-model="user.gender" value="女" id="woman" />
      <label for="woman">女</label>
      <input type="radio" v-model="user.gender" value="保密" id="secret" />
      <label for="secret">保密</label>
    </p>

    <!-- 4. 多选框：绑定数组 user.hobby -->
    <p>
      <label class="label">兴趣爱好：</label><br />
      <input type="checkbox" v-model="user.hobby" value="编程" id="code" />
      <label for="code">编程</label>
      <input type="checkbox" v-model="user.hobby" value="阅读" id="read" />
      <label for="read">阅读</label>
      <input type="checkbox" v-model="user.hobby" value="旅游" id="travel" />
      <label for="travel">旅游</label>
      <input type="checkbox" v-model="user.hobby" value="音乐" id="music" />
      <label for="music">音乐</label>
    </p>

    <!-- 5. 下拉框：城市 -->
    <p>
      <label class="label">所在城市：</label>
      <select v-model="user.city">
        <option value="" disabled>---- 请选择城市 ----</option>
        <option value="北京">北京</option>
        <option value="上海">上海</option>
        <option value="广州">广州</option>
        <option value="深圳">深圳</option>
        <option value="杭州">杭州</option>
      </select>
    </p>

    <!-- 6. 下拉框：学历 -->
    <p>
      <label class="label">最高学历：</label>
      <select v-model="user.education">
        <option value="" disabled>---- 请选择学历 ----</option>
        <option value="高中">高中</option>
        <option value="大专">大专</option>
        <option value="本科">本科</option>
        <option value="硕士">硕士</option>
        <option value="博士">博士</option>
      </select>
    </p>

    <!-- 操作按钮 -->
    <p class="btn-group">
      <button class="btn-submit" @click="handleSubmit">提交注册</button>
      <button class="btn-reset" @click="handleReset">重置表单</button>
    </p>

    <!-- 实时预览数据 -->
    <div class="preview-box">
      <p>实时表单数据（JSON格式）：</p>
      <pre>{{ user }}</pre>
    </div>
  </div>
</template>

<script setup>
import { reactive } from 'vue'

// 【工程化核心】使用 reactive 统一管理整个表单对象
const user = reactive({
  username: '',      // 文本框：字符串
  intro: '',         // 多行文本框：字符串
  gender: '',        // 单选框：字符串
  hobby: [],         // 【避坑】多选框：必须初始化为数组
  city: '',          // 下拉框：空字符串配合 disabled 占位
  education: ''      // 下拉框：空字符串
})

// 提交表单：打印 + 弹窗展示 JSON
const handleSubmit = () => {
  console.log('表单数据：', user)
  // JSON.stringify(user, null, 2)：第二个参数null是替换函数，第三个参数2是缩进空格数，用于格式化输出
  alert('注册成功！表单数据如下：\n\n' + JSON.stringify(user, null, 2))
}

// 重置表单：所有字段恢复初始值
const handleReset = () => {
  user.username = ''
  user.intro = ''
  user.gender = ''
  user.hobby = []
  user.city = ''
  user.education = ''
  console.log('表单已重置')
}
</script>

<style scoped>
.form-box {
  margin: 20px auto;
  width: 550px;
  border: 1px solid #eee;
  padding: 25px;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.08);
}
h3 {
  text-align: center;
  margin-bottom: 20px;
  color: #333;
}
p {
  margin: 15px 0;
}
.label {
  display: inline-block;
  width: 80px;
  text-align: right;
  margin-right: 10px;
  color: #555;
}
input[type="text"], textarea {
  width: 320px;
  padding: 8px;
  border: 1px solid #ccc;
  border-radius: 4px;
  font-size: 14px;
}
textarea {
  margin-top: 6px;
  margin-left: 90px;
  resize: vertical;
}
select {
  padding: 8px 10px;
  min-width: 180px;
  border: 1px solid #ccc;
  border-radius: 4px;
  font-size: 14px;
}
.btn-group {
  text-align: center;
  margin-top: 25px;
}
button {
  padding: 10px 25px;
  margin: 0 8px;
  cursor: pointer;
  border: none;
  border-radius: 4px;
  font-size: 14px;
}
.btn-submit {
  background-color: #42b983;
  color: #fff;
}
.btn-submit:hover {
  background-color: #3aa876;
}
.btn-reset {
  background-color: #f0f0f0;
  color: #333;
}
.btn-reset:hover {
  background-color: #e0e0e0;
}
.preview-box {
  margin-top: 25px;
  padding: 15px;
  background-color: #f9f9f9;
  border: 1px solid #eee;
}
.preview-box p {
  margin: 0 0 10px 0;
  font-weight: bold;
  color: #666;
}
pre {
  margin: 0;
  font-size: 13px;
  color: #333;
  white-space: pre-wrap;
  word-break: break-all;
}
</style>
