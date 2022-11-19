<template>
  <el-container style="height: 100vh">
    <el-container>
      <el-header>
        <div class="title">NbLSH</div>
      </el-header>
      <RouterView></RouterView>
    </el-container>
  </el-container>
</template>

<script lang="ts" setup></script>

<style scoped>
.el-header {
  position: relative;
  background-color: var(--el-color-primary-light-8);
  color: var(--el-text-color-border);
  text-align: center;
  font-size: 20px;
  font-weight: bolder;
}
.title {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  height: 100%;
}
</style>
