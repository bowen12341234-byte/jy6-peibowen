<template>
  <div class="modal">

    <div class="modal-header">
      <slot name="header">默认标题</slot>
    </div>

    <div class="modal-body">
      <slot>暂无内容</slot>
    </div>

    <div class="modal-footer">
      <slot name="footer">
        <button>默认关闭</button>
      </slot>
    </div>
  </div>
</template>

<style scoped>
.modal {
  width: 400px;
  border: 1px solid #ccc;
  border-radius: 8px;
  overflow: hidden;
  margin: 20px auto;
}
.modal-header {
  background: #f5f5f5;
  padding: 12px;
  font-weight: bold;
}
.modal-body {
  padding: 20px;
  min-height: 60px;
}
.modal-footer {
  padding: 12px;
  text-align: right;
  border-top: 1px solid #eee;
  background: #fafafa;
}
button {
  margin-left: 8px;
  padding: 6px 15px;
  cursor: pointer;
}
</style>