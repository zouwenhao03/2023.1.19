<script setup lang="ts">
import { ref } from "vue";

const awesome = ref(true);

function toggle() {
  //
  awesome.value == true ? (awesome.value = false) : (awesome.value = true);
}
</script>

<template>
  <div>
    <button @click="toggle">toggle</button>
    <h1 v-if="awesome">Vue is awesome!</h1>
    <h1 v-else>Oh no 😢</h1>
  </div>
</template>
