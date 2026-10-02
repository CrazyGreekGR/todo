<script setup lang="ts">
import InputBox from "@/components/inputBox.vue"
import tdi from "@/components/todoItem.vue"
import {ref} from "vue";

interface Todo {
  id: number
  name: string
  done: boolean
}

const todos = ref<Todo[]>([])

function addToDo(name: string) {
  todos.value.push({id: Date.now(), name: name, done: false})
}
</script>

<template>
  <div class="overall">
    <InputBox @add="addToDo" />
    <div class="todolist">
      <tdi v-for="todo in todos" :key="todo.id">{{todo.name}}</tdi>
    </div>
  </div>
</template>

<style>
body {
  background-color: #190f1f;
  color: white;
  font-family: Roboto,serif;
}
.todolist {
  display: flex;
  flex-direction: column;
  background-color: #201025;
  height: fit-content;
}
.overall {
  display: flex;
  flex-direction: column;
  width: 100%;
  max-width: 32rem;
  margin: 0 auto;
  padding: 1rem;
  box-sizing: border-box;
  gap: 1rem;
}
</style>
