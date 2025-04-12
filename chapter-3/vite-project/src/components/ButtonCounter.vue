<script setup>
import { ref } from 'vue'

const count = ref(0)
</script>

<template>
  <button @click="count++">現在 {{ count }} 回クリックされました</button>
</template>
