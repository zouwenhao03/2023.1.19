<script setup lang="ts">
import { computed, reactive, ref } from "vue";
import Child from '../components/child.vue';
import Son from '@/components/son.vue'
const str = ref('暂无信息')
const str2 = ref('son无消息')
let id = 0;
const msg = ref('父亲给儿子传的信息');
const obj = reactive({gift:'footerball'})
const newTodo = ref("");
const hideCompleted = ref(false);
const todos = ref([
  { id: id++, text: "Learn HTML", done: true },
  { id: id++, text: "Learn JavaScript", done: true },
  { id: id++, text: "Learn Vue", done: false },
]);

function addTodo() {
  todos.value.push({ id: id++, text: newTodo.value, done: false });
  newTodo.value = "";
}

function removeTodo(todo) {
  todos.value = todos.value.filter((t) => t !== todo);
}
const lesstodos = computed(()=>{
   return  hideCompleted.value ? todos.value.filter(i=>!i.done) : todos.value
}
 
)
</script>

<template>
  <div>
    <form @submit.prevent="addTodo">
      <input v-model="newTodo" />
      <button>Add Todo</button>
    </form>
    <ul>
      <li v-for="todo in lesstodos" :key="todo.id">
        <input type="checkbox" v-model="todo.done" />
        <span :class="{ done: todo.done }">{{ todo.text }}</span>
        <button @click="removeTodo(todo)">X</button>
      </li>
    </ul>
    <button @click="hideCompleted = !hideCompleted">
      {{ hideCompleted ? "Show all" : "Hide completed" }}
    </button>
    <Child  :msg='msg' :msg2='obj' @tofather="(msg)=>str=msg"/>
    {{str}}
    <Son  @send="(msg)=>{str2 = msg}"/>
    {{str2}}
  </div>
</template>

<style>
.done {
  text-decoration: line-through;
}
</style>
