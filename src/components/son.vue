<template>
  <div @click="sendMsg" class="son">
    <h1>son</h1>
  </div>
</template>

<script lang="ts" setup>
import { ref } from "@vue/reactivity";
const emit = defineEmits(["send"]);
const msg = ref("i am son msg to father");
function sendMsg() {
    
  emit("send", msg.value);
}
</script>

<style>
.son {
  border: 1px solid black;
  padding: 20px;
}
</style>
