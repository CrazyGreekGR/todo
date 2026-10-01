<script setup lang="ts">
import {ref} from "vue";

const todoItemName = ref('')
const emit = defineEmits(['add'])

function sendToDo() {
  if (todoItemName.value !== '') {
    emit('add', todoItemName.value)
    todoItemName.value = ''
  }
}

</script>

<template>
  <div class="overall">
    <div class="inputField">
      <input v-model="todoItemName" type="text">
      <button v-on:click="sendToDo()">Add</button>
    </div>
  </div>
</template>

<style scoped>
.overall {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  width: 100%;
  max-width: 32rem;
  margin: 0 auto;
  padding: 1rem;
  box-sizing: border-box;
}
.inputField {
  display: flex;
  gap: 10px;
}
input {
  flex: 1;
  min-width: 0;
  height: 2.75rem;
  border: none;
  font-size: 1.25rem;
  border-radius: 5px;
  background-color: #2e1c39;
  color: white;
  padding: 0 0.75rem;
}
button {
  flex-shrink: 0;
  border: none;
  padding: 0 1.25rem;
  border-radius: 10px;
  background-color: #2e1c39;
  color: white;
  cursor: pointer;
}
</style>