<script setup>
import { defineComponent } from 'vue'
import Section1Begin from './components/Section1Begin.vue'
import Section2Timeline from './components/Section2Timeline.vue'
import Section3Event from './components/Section3Event.vue'

import globalLogo from './assets/global-logo.png'
</script>

<template>
  <v-app>
    <v-app-bar color="primary" density="compact" scroll-behavior="collapse">
      <v-app-bar-title class="mx-0">
        <v-img
          class="mx-0"
          position="left"
          :src="globalLogo"
          height="48"
          :style="{ lineHeight: '48px', paddingLeft: '160px' }"
        >
          全脳アーキテクチャ若手の会の10年間を振り返る
        </v-img>
      </v-app-bar-title>

      <v-spacer></v-spacer>

      <v-btn
        class="ma-3"
        prepend-icon="mdi-calendar"
        href="https://wbawakate.connpass.com/event/325229/"
        target="_blank"
      >
        参加
      </v-btn>
    </v-app-bar>
    <v-main>
      <Section1Begin />
      <Section2Timeline />
      <Section3Event />
    </v-main>
  </v-app>
</template>
