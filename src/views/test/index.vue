<template>
  <div class="app-container">
    <div class="dashboard-text">测试</div>
    <el-button @click="fetchData">获取table</el-button>
    <div class="dashboard-text">{{ list }}</div>
  </div>
</template>
<script>
import { getList } from '@/api/table'
export default {
  data() {
    return {
      list: null,
      listLoading: true
    }
  },
  methods: {
    fetchData() {
      this.listLoading = true
      console.log('123')
      getList().then(response => {
        this.list = response.data.items
        console.log(this.list)
        this.listLoading = false
      })
    }
  }
}
</script>
