<script setup>
import Papa from 'papaparse'
import eventCsvStr from '../assets/event-sheet.csv?raw'

const basePath = '.'

const eventArr = Papa.parse(eventCsvStr, {
  header: true,
}).data.reverse()
</script>

<template>
  <v-container
    class="ma-0 pa-0 w-100"
    :style="{ position: 'relative', maxWidth: '100%' }"
  >
    <v-row class="ma-0 pa-0">
      <v-col class="ma-0 pa-0">
        <div
          :style="{
            position: 'absolute',
            left: 0,
            top: 0,
            width: '100%',
            height: '100vh',
          }"
        >
          <div
            v-for="(event, i) in eventArr"
            :style="{
              position: 'relative',
              top: 0,
              left: 0,
              width: '100%',
              height: '100%',
              clipPath: 'inset(0)',
            }"
          >
            <v-sheet
              color="black"
              :style="{
                position: 'fixed',
                top: 0,
                left: 0,
                width: '100%',
                height: '100vh',
                backgroundImage: `url(
                  ${basePath}/img/history/${event.year}-${
                  ('00' + event.month).slice(-2)
                }.jpg`,
                backgroundSize: 'cover',
                backgroundRepeat: 'no-repeat',
                backgroundPosition: 'center center',
              }"
            >
              <v-sheet
                :style="{
                  position: 'absolute',
                  top: 0,
                  left: 0,
                  width: '100%',
                  height: '100%',
                  background: `linear-gradient(
                    to right,
                    rgba(0, 0, 0, .65) 65%,
                    rgba(0, 0, 0, .25) 100%
                  )`,
                }"
              >
              </v-sheet>
            </v-sheet>
          </div>
        </div>
        <v-timeline
          class="pt-15"
          align="start"
          side="end"
          :style="{ rowGap: 0 }"
        >
          <v-timeline-item
            v-for="(event, i) in eventArr"
            :key="i"
            dot-color="indigo-darken-1"
            size="small"
            height="100vh"
            :data-idx="i"
          >
            <template v-slot:opposite>
              <!-- PC -->
              <div
                :class="`
                  d-none d-sm-flex pt-1
                  headline font-weight-bold text-indigo-lighten-4
                `"
                v-text="event.year + '年' + event.month + '月'"
              ></div>
            </template>
            <div>
              <!-- SP -->
              <div
                :class="`
                  d-flex d-sm-none pt-1 mb-3
                  headline font-weight-bold text-indigo-lighten-4
                `"
                v-text="event.year + '年' + event.month + '月'"
              ></div>
              <div :style="{ maxWidth: '80%' }">
                <h2
                  :class="`
                    mt-1 mb-4
                    headlinefont-weight-light text-indigo-lighten-4
                  `"
                  color="white"
                >
                  {{ event.ttl }}
                </h2>
                <div
                  class="text-indigo-lighten-4"
                  v-html="event.desc"
                ></div>
                <h3
                  v-if="event.news"
                  class="text-indigo-lighten-3 mt-6"
                >
                  AIニュース
                </h3>
                <p
                  class="text-indigo-lighten-3 ml-5"
                  v-html="event.news"
                ></p>
              </div>
            </div>
          </v-timeline-item>
        </v-timeline>
      </v-col>
    </v-row>
  </v-container>
</template>
