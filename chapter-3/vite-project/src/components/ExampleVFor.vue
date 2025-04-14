<script setup>
import { ref } from 'vue'

const itemArr = ref([
  {
    color: 'red',
    message: '赤いボタン',
  },
  {
    color: 'blue',
    message: '青いボタン',
  },
  {
    color: 'green',
    message: '緑のボタン',
  },
])
</script>

<template>
  <v-container>
    <h2>v-forの例</h2>
    <v-row>
      <v-col v-for="(item, index) in itemArr" key="index">
        <v-btn :color="item.color">{{ item.message }}</v-btn>
      </v-col>
    </v-row>
  </v-container>
</template>
