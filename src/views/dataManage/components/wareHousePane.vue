<template>
    <el-row :gutter="10">
        <el-col :xs="12" :sm="11" :md="10" :lg="8" :xl="6">
            <el-input placeholder="输入关键字进行过滤" v-model="filterText" class="input-with-select">
                <el-button slot="append">操作<i class="el-icon-arrow-up el-icon--right"></i></el-button>
            </el-input>
            <el-tree class="filter-tree" :data="tables" show-checkbox :props="defaultProps" default-expand-all :filter-node-method="filterNode" ref="tableTree"></el-tree>
        </el-col>
        <el-col :xs="12" :sm="13" :md="14" :lg="16" :xl="18">
            <el-table :data="table.values" style="width: 100%">
                <el-table-column v-for="(item, key, index) in table.column" :label="item" :key="index"></el-table-column>
            </el-table>
        </el-col>
    </el-row>
</template>
<style>
.filter-tree {
    margin-top:20px;
}
</style>
<script>
export default {
  data() {
      return {
        filterText: "",
        tables: [{
            "value": "ods",
            "label": "ods",
            loading: false,
            "children": [{
                "value": "wxg",
                "label": "wxg",
                "children": [
                    {
                        "value": "attribute_raw",
                        "label": "attribute_raw"
                    },
                    {
                        "value": "test_a",
                        "label": "test_a"
                    },
                    {
                        "value": "test_b",
                        "label": "test_b"
                    }
                ]
            }]
        }],
        table: {
            column: null,
            values: null
        },
        defaultProps: {
          children: 'children',
          label: 'label'
        }

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

    },
    getCheckedNodes() {
        console.log(this.$refs.tree.getCheckedNodes());
    },
    getCheckedNodes() {
        console.log(this.$refs.tree.getCheckedNodes());
    },
    filterNode(value, data) {
        if (!value) return true;
        return data.label.indexOf(value) !== -1;
    }
  },
  watch: {
      filterText(val) {
          this.$refs.tableTree.filter(val);
      }
  }
}
</script>
