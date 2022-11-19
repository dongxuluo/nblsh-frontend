<template>
  <el-container style="height: 100vh">
    <el-main class="form">
      <el-card class="box-card">
        <template #header>
          <div class="card-header">Result</div>
        </template>
        <el-table :data="tableData" style="width: 100%" height="450">
          <el-table-column prop="date" label="File" width="180" />
          <el-table-column prop="name" label="Size" width="180" />
          <el-table-column prop="address" label="Similarity" width="180" />
          <el-table-column label="Operate" width="180">
            <template #default="scope">
              <el-link type="primary" :href="scope.row.path"> detail </el-link>
            </template>
          </el-table-column>
        </el-table>
      </el-card>
    </el-main>
  </el-container>
</template>

<script lang="ts" setup>
const tableData = [
  {
    date: "2016-05-03",
    name: "Tom",
    address: "No. 189, Grove St, Los Angeles",
    path: "/compare",
  },
  {
    date: "2016-05-02",
    name: "Tom",
    address: "No. 189, Grove St, Los Angeles",
  },
  {
    date: "2016-05-04",
    name: "Tom",
    address: "No. 189, Grove St, Los Angeles",
  },
  {
    date: "2016-05-01",
    name: "Tom",
    address: "No. 189, Grove St, Los Angeles",
  },
  {
    date: "2016-05-01",
    name: "Tom",
    address: "No. 189, Grove St, Los Angeles",
  },
  {
    date: "2016-05-01",
    name: "Tom",
    address: "No. 189, Grove St, Los Angeles",
  },
  {
    date: "2016-05-01",
    name: "Tom",
    address: "No. 189, Grove St, Los Angeles",
  },
  {
    date: "2016-05-01",
    name: "Tom",
    address: "No. 189, Grove St, Los Angeles",
  },
  {
    date: "2016-05-01",
    name: "Tom",
    address: "No. 189, Grove St, Los Angeles",
  },
];
</script>

<style scoped>
.el-main {
  background-color: var(--el-color-primary-light-9);
}
.upload {
  /* display: inline-flex; */
  align-items: center;
  justify-content: center;
  height: 100%;
}
.card-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.box-card {
  margin-top: 100px;
  margin-left: auto;
  margin-right: auto;
  width: 800px;
}
</style>
