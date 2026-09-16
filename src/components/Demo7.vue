<template>
  <div class="form-box">
    <h3>用户兴趣与信息表单</h3>

    <!-- 1. 多选框：绑定数组，自动追加/删除 -->
    <p>
      <label>兴趣爱好（可多选）：</label><br />
      <input type="checkbox" v-model="user.hobby" value="游戏" id="game" />
      <label for="game">游戏</label>

      <input type="checkbox" v-model="user.hobby" value="阅读" id="read" />
      <label for="read">阅读</label>

      <input type="checkbox" v-model="user.hobby" value="旅游" id="travel" />
      <label for="travel">旅游</label>

      <input type="checkbox" v-model="user.hobby" value="音乐" id="music" />
      <label for="music">音乐</label>

      <input type="checkbox" v-model="user.hobby" value="运动" id="sport" />
      <label for="sport">运动</label>
    </p>

    <!-- 2. 下拉框：注意占位符 disabled -->
    <p>
      <label>所在城市：</label>
      <select v-model="user.city">
        <!-- 占位符：disabled 防止用户误选空值 -->
        <option value="" disabled>--- 请选择城市 ---</option>
        <option value="北京">北京</option>
        <option value="上海">上海</option>
        <option value="广州">广州</option>
        <option value="深圳">深圳</option>
        <option value="杭州">杭州</option>
      </select>
    </p>

    <!-- 3. 下拉框：学历，默认选中"本科" -->
    <p>
      <label>最高学历：</label>

      <select v-model="user.education">
        <option value="" disabled>--- 请选择学历 ---</option>
        <option value="高中">高中</option>
        <option value="大专">大专</option>
        <option value="本科">本科</option>
        <option value="硕士">硕士</option>
        <option value="博士">博士</option>
      </select>
    </p>

    <!-- 实时预览数据 -->
    <div class="preview-box">
      <p>实时表单数据：</p>
      <pre>{{ user }}</pre>
    </div>
  </div>
</template>

<script setup>
import { reactive } from 'vue'

const user = reactive({
  hobby: [],
  city: '',
  education: ''
})
</script>

<style scoped>
.form-box {
  margin: 20px auto;
  width: 500px;
  border: 1px solid #eee;
  padding: 20px;
  border-radius: 8px;
}
p {
  margin: 15px 0;
}
select {
  padding: 6px 10px;
  min-width: 150px;
  border: 1px solid #ccc;
  border-radius: 4px;
}
.preview-box {
  margin-top: 20px;
  padding: 10px;
  background-color: #f9f9f9;
  border-radius: 4px;
}
pre {
  margin: 0;
  font-size: 14px;
}
</style>