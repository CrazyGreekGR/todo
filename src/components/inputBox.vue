<script setup lang="ts">

</script>

<template>
  <div>
    <input type="text">
    <button>Add</button>
  </div>
</template>

<style scoped>
  div {
    display: flex;
    flex-direction: row;
    overflow: hidden;
    width: fit-content;
    height: fit-content;
    align-self: center;
    margin-left: auto;
    margin-right: auto;
    gap: 20px
  }
  input {
    width: 30vw;
    height: 5vh;
    border: none;
    font-size: x-large;
    border-radius: 5px;
    background-color: #2e1c39;
    color: white;
  }
  button {
    border: none;
    width: 60px;
    border-radius: 10px;
    background-color: #2e1c39;
    color: white;
    cursor: pointer;
  }
</style>