<!-- src/components/GoodsTable.vue -->
<template>
  <table class="gt">
    <thead>
      <tr>
        <th v-for="col in columns" :key="col.prop">{{ col.label }}</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="(row, i) in data" :key="row.id">
        <td v-for="col in columns" :key="col.prop">
          <slot :name="col.slot" :row="row" :index="i">
            {{ row[col.prop] }}
          </slot>
        </td>
      </tr>
      <tr v-if="data.length === 0">
        <td :colspan="columns.length" class="empty">
          <slot name="empty">暂无数据</slot>
        </td>
      </tr>
    </tbody>
  </table>
</template>

<script setup>
defineProps({
  columns: { type: Array, required: true, default: () => [] },
  data: { type: Array, required: true, default: () => [] }
});
</script>

<style scoped>
.gt {
  width: 100%;
  border-collapse: collapse;
  font-size: 14px;
}
.gt th,
.gt td {
  border-bottom: 1px solid #ebeef5;
  padding: 10px 12px;
  text-align: left;
}
.gt th {
  background: #f5f7fa;
  color: #606266;
  font-weight: 600;
}
.gt tr:hover td {
  background: #f5f7fa;
}
.empty {
  text-align: center;
  color: #909399;
  padding: 30px 0 !important;
}
</style>