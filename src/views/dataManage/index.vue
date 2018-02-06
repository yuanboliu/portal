<template>
  <div class="tab-container">
    <el-tabs style='margin-top:15px;' v-model="activeName" type="border-card">
      <el-tab-pane label="数据仓库" name="warehouse">
        <keep-alive>
          <ware-house-pane></ware-house-pane>
        </keep-alive>
      </el-tab-pane>
      <el-tab-pane label="hdfs 目录" name="hdfs">
        <keep-alive>
          <tab-pane></tab-pane>
        </keep-alive>
      </el-tab-pane>
      <el-tab-pane label="回收站" name="trash">
        <keep-alive>
          <tab-pane></tab-pane>
        </keep-alive>
      </el-tab-pane>
    </el-tabs>
  </div>
</template>

<script>
import tabPane from './components/tabPane'
import wareHousePane from './components/wareHousePane'

export default {
  name: 'tab',
  components: { tabPane, wareHousePane},
  data() {
    return {
      activeName: 'wareHouse',
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
