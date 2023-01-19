<template>
  <div class="about">
    <h1 :class="titleClass">This is an about page</h1>
    <div :class="d1Class">Test</div>
  </div>
</template>

<script lang="ts" setup>
/*
绑定动态class
1.style中class样式类名
2.script中使用ref变成响应式变量
3.使用:class绑定
*/
import { ref } from "vue";
const titleClass = ref("title");
const d1Class = ref("d1");
</script>
<style>
.title {
  color: red;
}
.d1 {
  color: green;
  font-size: 32px;
}
</style>
