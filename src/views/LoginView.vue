<template>
  <el-container style="height: 100vh">
    <el-main class="form">
      <el-card class="box-card">
        <template #header>
          <div class="card-header">Login</div>
        </template>
        <el-form
          :label-position="labelPosition"
          label-width="100px"
          :model="formLabelAlign"
          style="max-width: 460px"
        >
          <el-form-item label="Username">
            <el-input
              v-model="formLabelAlign.username"
              placeholder="Please input user name"
            />
          </el-form-item>
          <el-form-item label="Password">
            <el-input
              v-model="formLabelAlign.password"
              type="password"
              placeholder="Please input password"
              show-password
            />
          </el-form-item>
          <el-form-item>
            <el-button type="primary" @click="login"> Login </el-button>
            <el-button @click="reset"> Reset </el-button>
          </el-form-item>
        </el-form>
      </el-card>
    </el-main>
  </el-container>
</template>

<script lang="ts" setup>
import { ref, reactive } from "vue";
import router from "@/router";
const labelPosition = ref("right");

const formLabelAlign = reactive({
  username: "",
  password: "",
});

const login = () => {
  router.push("/upload");
};

const reset = () => {
  formLabelAlign.username = "";
  formLabelAlign.password = "";
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
