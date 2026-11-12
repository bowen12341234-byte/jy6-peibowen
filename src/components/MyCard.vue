<template>
  <div class="my-card">
    <div class="my-card-head">
      
      <slot name="title">卡片默认标题</slot>
    </div>
    <div class="my-card-body">
      
      <slot>暂无内容，请在组件标签中间传入内容</slot>
    </div>
  </div>
</template>

<script setup>

</script>

<style scoped>
.my-card {
  width: 320px;
  border: 1px solid #dcdfe6;
  border-radius: 8px;
  overflow: hidden;
  margin: 20px auto;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.06);
}
.my-card-head {
  background: #f5f7fa;
  padding: 12px 16px;
  font-weight: bold;
  border-bottom: 1px solid #ebeef5;
}
.my-card-body {
  padding: 16px;
  color: #606266;
}
</style>