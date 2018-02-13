<template>
  <div class="tab-container">
    <el-tabs style='margin-top:15px;' v-model="activeName" type="border-card">
      <el-tab-pane label="数据仓库" name="warehouse">
        <keep-alive>
          <warehouse-pane></warehouse-pane>
        </keep-alive>
      </el-tab-pane>
      <el-tab-pane label="hdfs 目录" name="hdfs">
        <keep-alive>
          <hdfs-pane></hdfs-pane>
        </keep-alive>
      </el-tab-pane>
      <el-tab-pane label="回收站" name="trash">
        <keep-alive>
          <trash-pane></trash-pane>
        </keep-alive>
      </el-tab-pane>
    </el-tabs>
  </div>
</template>

<script>
import hdfsPane from './components/hdfsPane'
import warehousePane from './components/warehousePane'
import trashPane from './components/trashPane'

export default {
  name: 'tab',
  components: { hdfsPane, warehousePane, trashPane},
  data() {
    return {
      activeName: 'warehouse',
      createdTimes: 0
    }
  },
  methods: {
    showCreatedTimes() {
      this.createdTimes = this.createdTimes + 1
    }
  }
}
</script>

<style scoped>
  .tab-container{
    margin: 30px;
  }
</style>
