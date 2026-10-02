<script setup lang="ts"></script>

<template>
  <div class="tdiOverall">
    <p><slot /></p>
    <input type="checkbox">
  </div>
</template>

<style scoped>
.tdiOverall {
  display: flex;
  flex-direction: row;
  align-items: center;
  gap: 390px;
}
p {
  font-size: 1.1rem;
  margin: 0;
}
input {
  appearance: none;
  margin-left: auto;
  width: 1.5rem;
  height: 1.5rem;
  border: 2px solid #94a3b8;
  border-radius: 50%;
  cursor: pointer;
}
input:checked {
  background: #fb923c;
  border-color: #fb923c;
}
.tdiOverall:has(input:checked) p {
  text-decoration: line-through;
  color: #6c6c6c;
}
</style>