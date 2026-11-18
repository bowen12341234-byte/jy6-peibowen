<template>
  <h1>子组件</h1>
  <div v-for="good in goodList" >
    <slot :item="good">
      {{ good.id }} {{ good.gname }} {{ good.price }}
    </slot>
  </div>
</template>

<script setup>
defineProps({
  goodList: {
    type: Array,
    default: () => [{ id: 200, gname: "康师傅", price: 2 }]
  }
})
</script>