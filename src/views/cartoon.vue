<script setup lang="ts">
import { ref } from 'vue';
const count = ref(0);
</script>

<template>
 <el-row :gutter="10">
    <el-col :xs="8" :sm="6" :md="4" :lg="3" :xl="1"
      ><div class="grid-content grid-bisque"
    /></el-col>
    <el-col :xs="4" :sm="6" :md="8" :lg="9" :xl="11"
      ><div class="grid-content grid-blue"
    /></el-col>
    <el-col :xs="4" :sm="6" :md="8" :lg="9" :xl="11"
      ><div class="grid-content grid-red"
    /></el-col>
    <el-col :xs="8" :sm="6" :md="4" :lg="3" :xl="1"
      ><div class="grid-content grid-yellow"
    /></el-col>
  </el-row>
</template>

<style scoped>
.el-row {
  margin-bottom: 20px;
}

.el-col {

}

.grid-content {
  min-height: 36px;
}
.grid-bisque{
  background-color: bisque;
}
.grid-yellow{
  background-color: yellow;
}
.grid-red{
  background-color: red;
}
.grid-blue{
  background-color: lightblue;
}
.download{
    background: #fb7299;
    border-radius: 1.25rem;
    font-size: 13px;
    color: #fff;
    text-align: center;
    padding: 0 16px;
    height:30px;
    line-height: 30px;
}
</style>
