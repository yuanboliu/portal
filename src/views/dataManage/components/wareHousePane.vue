<template>
    <div class="block">
    <el-cascader placeholder="试试搜索：ods" :options="tables" filterable></el-cascader>
    <el-table :data="table.values" style="width: 100%">
        <el-table-column v-for="(item, key, index) in table.column" :label="item" :key="index"></el-table-column>
    </el-table>
    </div>
</template>

<script>
export default {
  data() {
      return {
        tables: null,
        table: {
            column: null,
            values: null
        },
      }
  },
  created() {
      this.getTableList()
  },
  methods: {
    getTableList() {
        // 获取到所有的列表
    },
    getColumnList() {

    }
  }
}
</script>
