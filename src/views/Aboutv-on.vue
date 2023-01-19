<template>
  <div class="about">
    <div>{{ count }}</div>
    <button @click="increment">addcount</button>
  </div>
</template>

<script lang="ts" setup>
/*
绑定事件：
v-on简写@

 */
import { isInDestructureAssignment } from "@vue/compiler-core";
import { ref } from "vue";
const count = ref(0);
//写法1：
function increment(){
  count.value ++
}
//写法2：
/*
const increment = ()=>{
  count.value++;
};
*/
</script>
<style></style>
