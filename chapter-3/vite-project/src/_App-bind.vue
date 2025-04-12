<script setup>
const exampleMessage = 'Hello, world!'
const textColor = '#ff0000'
</script>

<template>
  <h1>Vueサンプル</h1>

  <h2>データバインディングの例</h2>
  <p :style="{ color: textColor }">{{ exampleMessage }}</p>
</template>
