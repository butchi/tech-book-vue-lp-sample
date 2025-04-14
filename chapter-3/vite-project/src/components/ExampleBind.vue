<script setup>
const exampleMessage = 'Hello, world!'
const exampleStyle = { color: '#ff0000' }
</script>

<template>
  <v-container>
    <h2>データバインディングの例</h2>
    <p :style="exampleStyle">{{ exampleMessage }}</p>
  </v-container>
</template>
