<template>
  <h1 style="text-align: center">按需引入示例</h1>
  <el-config-provider :locale="zhCn">
    <pure-table border :loading="loading" :data="tableData" :columns="columns" :pagination="pagination"></pure-table>
  </el-config-provider>
</template>

<script lang="ts" setup>
import { ref, reactive } from "vue"
import type { TableColumns } from "@pureadmin/table"
import zhCn from "element-plus/es/locale/lang/zh-cn"

const columns: Array<TableColumns> = [{
  label: "Date",
  prop: "date",
}, {
  label: "Name",
  prop: "name",
}, {
  label: "Address",
  prop: "address",
}]

const tableData = [
  {
    date: '2016-05-03',
    name: 'Tom',
    address: 'No. 189, Grove St, Los Angeles',
  },
  {
    date: '2016-05-02',
    name: 'Tom',
    address: 'No. 189, Grove St, Los Angeles',
  },
  {
    date: '2016-05-04',
    name: 'Tom',
    address: 'No. 189, Grove St, Los Angeles',
  },
  {
    date: '2016-05-01',
    name: 'Tom',
    address: 'No. 189, Grove St, Los Angeles',
  },
]

let loading = ref(true)
const pagination = reactive({
  pageSize: 5,
  currentPage: 1,
  background: true,
  total: tableData.length
})

setTimeout(()=>{
  loading.value = false
},1500)
</script>

