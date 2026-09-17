<template>
    <h2>用户注册</h2>
    <form action="#" method="post">
        <!-- 文本框 -->
        <fieldset>
            <legend>基本信息</legend>
            <p>
                <label for="username">用户名：</label>
                <input type="text" id="username" name="username" v-model="user.username" placeholder="请输入用户名" required>
            </p>
            <p>
                <label for="password">密码：</label>
                <input type="password" id="password" name="password" v-model="user.password" placeholder="请输入密码" required>
            </p>
            <p>
                <label for="confirmPassword">确认密码：</label>
                <input type="password" id="confirmPassword" name="confirmPassword" v-model="user.confirmPassword" placeholder="请再次输入密码" required>
            </p>
            <p>
                <label for="email">邮箱：</label>
                <input type="email" id="email" name="email" v-model="user.email" placeholder="请输入邮箱地址">
            </p>
            <p>
                <label for="phone">手机号：</label>
                <input type="tel" id="phone" name="phone" v-model="user.phone" placeholder="请输入手机号">
            </p>
        </fieldset>

        <!-- 单选框 -->
        <fieldset>
            <legend>个人信息</legend>
            <p>性别：</p>
            <p>
                <input type="radio" id="male" name="gender" v-model="user.gender" value="male" checked>
                <label for="male">男</label>
                <input type="radio" id="female" name="gender" v-model="user.gender" value="female">
                <label for="female">女</label>
                <input type="radio" id="secret" name="gender" v-model="user.gender" value="secret">
                <label for="secret">保密</label>
            </p>

            <!-- 下拉列表 -->
            <p>
                <label for="province">所在省份：</label>
                <select id="province" name="province" v-model="user.province">
                    <option value="">--请选择省份--</option>
                    <option value="beijing">北京市</option>
                    <option value="shanghai">上海市</option>
                    <option value="guangdong">广东省</option>
                    <option value="zhejiang">浙江省</option>
                    <option value="jiangsu">江苏省</option>
                    <option value="sichuan">四川省</option>
                    <option value="other">其他</option>
                </select>
            </p>
            <p>
                <label for="city">所在城市：</label>
                <select id="city" name="city" v-model="user.city">
                    <option value="">--请选择城市--</option>
                    <option value="city1">城市1</option>
                    <option value="city2">城市2</option>
                    <option value="city3">城市3</option>
                    <option value="city4">城市4</option>
                </select>
            </p>

            <!-- 多选框 -->
            <p>兴趣爱好：</p>
            <p>
                <input type="checkbox" id="reading" name="hobby" v-model="user.hobby" value="reading">
                <label for="reading">阅读</label>
                <input type="checkbox" id="sports" name="hobby" v-model="user.hobby" value="sports">
                <label for="sports">运动</label>
                <input type="checkbox" id="music" name="hobby" v-model="user.hobby" value="music">
                <label for="music">音乐</label>
                <input type="checkbox" id="travel" name="hobby" v-model="user.hobby" value="travel">
                <label for="travel">旅行</label>
                <input type="checkbox" id="game" name="hobby" v-model="user.hobby" value="game">
                <label for="game">游戏</label>
                <input type="checkbox" id="movie" name="hobby" v-model="user.hobby" value="movie">
                <label for="movie">电影</label>
            </p>
        </fieldset>

        <!-- 文本域 -->
        <fieldset>
            <legend>补充信息</legend>
            <p>
                <label for="bio">个人简介：</label><br>
                <textarea id="bio" name="bio" rows="5" cols="40" v-model="user.bio" placeholder="请简单介绍一下自己..."></textarea>
            </p>
        </fieldset>

        <!-- 提交与重置按钮 -->
        <p>
            <input type="submit" value="注册">
            <!--input type="reset" value="重置"-->
            <button @click="clean">重置</button>
        </p>
    </form>
    <fieldset>
        <legend></legend>
        <div>
            {{user}}
        </div>
    </fieldset>
</template>

<script setup>
import { reactive, ref } from "vue";

/*const username = ref('admin')
const password = ref('')
const confirmPassword = ref('')
const email = ref('')
const phone = ref('')
const gender = ref('male')
const province = ref('')
const city = ref('')
const hobby = ref([])
const bio = ref('')*/

const user = reactive({
    username:'',
    password:'',
    confirmPassword:'',
    email:'',
    phone:'',
    gender:'',
    province:'',
    city:'',
    hobby:[],
    bio:''
})

const clean = ()=>{
    user.username = '',
    user.password='',
    user.confirmPassword='',
    user.email='',
    user.phone='',
    user.gender='',
    user.province='',
    user.city='',
    user.hobby=[],
    user.bio=''
}
</script>

<style scoped>


</style> /