<script setup>
const rawHtml = '<span style="color: red">赤いテキスト</span>'
</script>

<template>
  <v-container>
    <h2>v-htmlの例</h2>
    <p>HTMLテキストをそのまま表示: {{ rawHtml }}</p>
    <p>v-htmlを使ってHTMLを埋め込み: <span v-html="rawHtml"></span></p>
  </v-container>
</template>
