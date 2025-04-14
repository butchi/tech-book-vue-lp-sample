<script setup>
import ExampleComponent from './components/ExampleComponent.vue'
import ExampleBind from './components/ExampleBind.vue'
import ExampleVFor from './components/ExampleVFor.vue'
import ExampleVIf from './components/ExampleVIf.vue'
import ExampleVHtml from './components/ExampleVHtml.vue'
</script>

<template>
  <v-app>
    <v-main>
      <v-container>
        <h1>Vueサンプル</h1>

        <ExampleComponent />

        <ExampleBind />

        <ExampleVFor />

        <ExampleVIf />

        <ExampleVHtml />
      </v-container>
    </v-main>
  </v-app>
</template>
