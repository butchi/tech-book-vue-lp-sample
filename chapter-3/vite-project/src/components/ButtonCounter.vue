<script setup>
import { ref } from 'vue'

const count = ref(0)
</script>

<template>
  <button @click="count++">
    現在 {{ count }} 回クリックされました
  </button>
</template>

<style scoped>
button {
  border-radius: 5px;
  background-color: lightgray;
  border-color: gray;
  border-style: solid;
  border-width: 1px;
  padding: 1px 7px 2px;
  margin: 0em;
}
</style>