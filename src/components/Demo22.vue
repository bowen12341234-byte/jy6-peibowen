<!--<template>
    <h1>搜索框</h1>
    {{ good }}
</template>
<script setup>

</script>-->
<template>
  <h1>商品展示</h1>
  {{ goods.id }}
  {{ goods.gname }}
  {{ goods.price }}
  {{ goods.a }}
  {{ tag }}
</template>

<script setup>
/* defineProps({ ... */
defineProps({
  goods: {
    type: Object,
    /* default(){
      return {id:100,gname:"拯救者",price:8000}
    } */
    default: () => ({ id: 100, gname: "拯救者", price: 8000 })
  },
  tag: {
    type: Array,
    default: () => ['电脑', '学习用具']
  }
})
</script>