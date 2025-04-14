<script setup>
import { ref } from 'vue'

// const num = ref(1)
// const num = ref(2)
const num = ref(3)
// const num = ref(4)
// const num = ref(5)
</script>

<template>
  <v-container>
    <h2>v-ifの例</h2>
    <v-row>
      <v-col cols="12">
        <v-btn v-if="num === 1">ボタンA</v-btn>
        <v-btn v-if="num === 2">ボタンB</v-btn>
        <v-btn v-if="num === 3">ボタンC</v-btn>
        <v-btn v-else>ボタンD</v-btn>
      </v-col>
    </v-row>
  </v-container>
</template>
