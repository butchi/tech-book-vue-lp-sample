<template>
  <v-container>
    <v-row>
      <h2>ボタンのサンプル</h2>
    </v-row>
    <v-row>
      <v-col>
        <v-btn>無地のボタン</v-btn>
      </v-col>
      <v-col>
        <v-btn color="primary">Primary</v-btn>
      </v-col>
      <v-col>
        <v-btn color="secondary">Secondary</v-btn>
      </v-col>
      <v-col>
        <v-btn color="primary" rounded>rounded</v-btn>
      </v-col>
      <v-col>
        <v-btn color="primary" variant="outlined">outlined</v-btn>
      </v-col>
      <v-col>
        <v-btn
          prepend-icon="mdi-share"
          class="ma-2"
          color="indigo"
          rounded
          size="x-small"
        >
          シェア
        </v-btn>
      </v-col>
    </v-row>
  </v-container>
</template>