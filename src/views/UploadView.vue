<template>
  <el-container style="height: 100vh">
    <el-main class="form">
      <el-card class="box-card">
        <template #header>
          <div class="card-header">Upload</div>
        </template>
        <el-upload
          v-model:file-list="fileList"
          class="upload"
          action="https://run.mocky.io/v3/9d059bf9-4660-45f2-925d-ce80ad6c4d15"
          multiple
          :on-preview="handlePreview"
          :on-remove="handleRemove"
          :before-remove="beforeRemove"
          :limit="1"
          :on-exceed="handleExceed"
        >
          <el-button type="primary">Click to upload</el-button>
          <template #tip>
            <div class="el-upload__tip">
              txt files with a size less than 500KB.
            </div>
          </template>
        </el-upload>
        <el-form>
          <el-form-item>
            <el-button type="primary" @click="finish"> Finish </el-button>
          </el-form-item>
        </el-form>
      </el-card>
    </el-main>
  </el-container>
</template>
<script lang="ts" setup>
import { ref } from "vue";
import { ElMessage, ElMessageBox } from "element-plus";

import type { UploadProps, UploadUserFile } from "element-plus";
import router from "@/router";

const fileList = ref<UploadUserFile[]>([
  {
    name: "1.txt",
    url: "https://element-plus.org/images/element-plus-logo.svg",
  },
]);

const handleRemove: UploadProps["onRemove"] = (file, uploadFiles) => {
  console.log(file, uploadFiles);
};

const handlePreview: UploadProps["onPreview"] = (uploadFile) => {
  console.log(uploadFile);
};

const handleExceed: UploadProps["onExceed"] = (files, uploadFiles) => {
  ElMessage.warning(
    `The limit is 1, you selected ${files.length} files this time, add up to 
    ${files.length + uploadFiles.length} totally`
  );
};

const beforeRemove: UploadProps["beforeRemove"] = (uploadFile) => {
  return ElMessageBox.confirm(
    `Cancel the transfert of ${uploadFile.name} ?`
  ).then(
    () => true,
    () => false
  );
};

const finish = () => {
  router.push("/result");
};
</script>

<style scoped>
.el-main {
  background-color: var(--el-color-primary-light-9);
}
.card-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.box-card {
  margin: auto;
  margin-top: 100px;
  width: 480px;
}
</style>
