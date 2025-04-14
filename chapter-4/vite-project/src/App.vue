<script setup>
import ExampleVBtn from './components/ExampleVBtn.vue'
import ExampleVCard from './components/ExampleVCard.vue'
import ExampleVChip from './components/ExampleVChip.vue'
</script>

<template>
  <v-app>
    <v-main>
      <v-container>
        <h1>Vuetifyサンプル</h1>

        <ExampleVBtn />

        <ExampleVCard />

        <ExampleVChip />
      </v-container>
    </v-main>
  </v-app>
</template>
