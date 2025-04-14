<script setup>
import { ref } from 'vue'
const count = ref(0)

const increment = () => {
  count.value++
}
</script>

<template>
  <v-container>
    <h2>リアクティブの例</h2>
    <p>カウント: {{ count }}</p>
    <button @click="increment">カウントアップ</button>
  </v-container>
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