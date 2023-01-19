<script setup lang="ts">
import { ref } from "vue";

// 给每个 todo 对象一个唯一的 id
let id = 0;

const newTodo = ref("");
const todos = ref([
  { id: id++, text: "Learn HTML" },
  { id: id++, text: "Learn JavaScript" },
  { id: id++, text: "Learn Vue" },
]);

function addTodo() {
  // ...
  if(newTodo.value){
   todos.value = [...todos.value,{id:id++,text:newTodo.value}];
   console.log(todos.value)
   newTodo.value = ''
  }
}

function removeTodo(todo) {
  // ...
    todos.value = todos.value.filter((t) => t !== todo)
    console.log(todos.value)
}
</script>

<template>
  <div>
    <form @submit.prevent="addTodo">
      <input v-model="newTodo" />
      <button @click="addTodo">Add Todo</button>
    </form>
    <ul>
      <li v-for="todo in todos" :key="todo.id">
        {{ todo.text }}
        <button @click="removeTodo(todo)">X</button>
      </li>
    </ul>
  </div>
</template>
