<template>
    <ul>
        <li v-for="(shop,index) in shoppings" :key="shop.id">
           <div>
               <p>{{index}}</p>
               <img :src="shop.shopimg" alt="">
               <p class="a">{{ shop.shopname }}</p>
               <p class="b">{{ shop.shoptag }}</p>
               <p class="c">{{ shop.shopprice }}</p>
            </div>
        </li>
    </ul>
    <ol>
        <li v-for="a in arrys" :key="a">{{ a }}</li>
    </ol>
</template>
<script setup>
import { reactive } from "vue";
import imgsrc from '../assets/hero.png'
    const arrys = [1,2,3,4,5,6,7,8,9]
    const shoppings = reactive([
        {
           shopimg : imgsrc,
           shopname: '瓜子',
           shoptag: '坚果',
           shopprice: '6'
        },
        {
           shopimg : imgsrc,
           shopname: '糖果',
           shoptag: '糖',
           shopprice: '5'
        }
    ])
</script>