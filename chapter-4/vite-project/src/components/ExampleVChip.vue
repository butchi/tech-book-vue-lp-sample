<template>
  <v-container>
    <v-row>
      <h2>チップのサンプル</h2>
    </v-row>
    <v-row>
      <v-chip class="ma-2">無地のChip</v-chip>

      <v-chip class="ma-2" color="primary">Primary</v-chip>

      <v-chip
        class="ma-2"
        color="indigo"
        prepend-icon="mdi-account-circle"
      >
        Mike
      </v-chip>

      <v-chip append-icon="mdi-star" class="ma-2" color="orange">
        Premium
      </v-chip>

      <v-chip append-icon="mdi-cake-variant" class="ma-2" color="primary">
        1 Year
      </v-chip>
    </v-row>
  </v-container>
</template>