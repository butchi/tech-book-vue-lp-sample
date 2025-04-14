<script setup>
const exampleMessage = 'Hello, world!'
const textColor = '#ff0000'
</script>

<template>
  <v-container>
    <h2>データバインディングの例</h2>
    <p :style="{ color: textColor }">{{ exampleMessage }}</p>
  </v-container>
</template>
