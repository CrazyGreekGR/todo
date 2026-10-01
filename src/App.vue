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
  <InputBox @add="addToDo" />
  <div class="todolist">
    <tdi v-for="todo in todos" :key="todo.id">{{todo.name}}</tdi>
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
  width: fit-content;
  background-color: #201025;
  height: fit-content;
  margin-left: 34.35%;
  margin-right: auto;
}
</style>
