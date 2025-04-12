<script setup>
import { marked } from 'marked'

import lineup1Md from '../assets/lineup-1.md?raw'
import lineup2Md from '../assets/lineup-2.md?raw'
import lineup3Md from '../assets/lineup-3.md?raw'
import appendixMd from '../assets/appendix.md?raw'

const basePath = '.'

const lineupArr = [
  {
    title: '13:00 ~ 13:50 これまでの10年編',
    mdTxt: lineup1Md,
  },
  {
    title: '14:00 ~ 14:50 現在編',
    mdTxt: lineup2Md,
  },
  {
    title: '15:00 ~ 15:50 これからの10年編',
    mdTxt: lineup3Md,
  },
  {
    title: '16:00 ~ 17:00 ネットワーキング',
  },
]

lineupArr.forEach((lineup) => {
  if (!lineup.mdTxt) return

  lineup.mdHtml = marked.parse(lineup.mdTxt)
})

const appendixHtml = marked.parse(appendixMd)
</script>

<template>
  <v-container>
    <v-row class="ma-0 pa-0">
      <v-col class="ma-0 pa-0">
        <v-card
          class="mx-auto my-12"
          :style="{
            backgroundImage: `linear-gradient(
              to bottom,
              rgba(0, 0, 0, .65) 0%,
              rgba(255, 255, 255, 1) 25%),
              url(${basePath}/img/cover-fade.jpg)
            `,
            backgroundPosition: 'center top, center top',
            backgroundSize: '100%, 100%',
            backgroundRepeat: 'no-repeat, no-repeat',
          }"
        >
          <v-card-text>
            <h2 class="text-white">
              <v-icon left>mdi-calendar</v-icon>
              【WBA若手 10周年記念】AIの10年間を振り返る
            </h2>
            <p class="mt-3 text-white">
              全脳アーキテクチャ若手の会は当時大学生だったメンバーを中心に発足し、それから大きく成長していきました。
              それから10年間の月日が流れ、AIの研究開発の状況も大きく進展しました。
              本イベントは、当会の設立10周年を記念イベントとして、これまでの10年、現在、それから今後の10年間について、改めて議論をします。
            </p>
            <v-divider class="my-3"></v-divider>
            <h3 class="mb-3 text-white">スケジュール</h3>
            <!-- SP -->
            <div class="d-md-none">
              <div
                v-for="lineup in lineupArr"
                class="mx-auto"
                icon="mdi-clock-outline"
              >
                <v-card
                  class="mt-3"
                  :style="{
                    backgroundColor: 'rgba(255, 255, 255, 0.65)'
                  }"
                >
                  <v-card-text>
                    <h4
                      v-if="lineup.title"
                      v-html="lineup.title"
                      class="text-h6"
                    ></h4>
                    <div
                      v-if="lineup.mdHtml"
                      v-html="lineup.mdHtml"
                      class="mt-3 lineup-text"
                    ></div>
                  </v-card-text>
                </v-card>
              </div>
              <h3 class="mt-3">イベント詳細</h3>
              <p class="mt-3">
                <span class="font-weight-bold">開催日</span>:
                2024年8月17日 13:00 〜 17:00
              </p>
              <p class="mt-3">
                <span class="font-weight-bold">イベントURL</span>:
                <a
                  href="https://wbawakate.connpass.com/event/325229/"
                  target="_blank"
                  >https://wbawakate.connpass.com/event/325229/</a
                >
              </p>
              <div v-html="appendixHtml" class="appendix-text"></div>
            </div>
            <!-- PC -->
            <div class="d-none d-md-block">
              <v-timeline
                align-top
                side="end"
                dot-color="blue-darken-1"
              >
                <v-timeline-item
                  v-for="lineup in lineupArr"
                  class="mx-auto"
                  icon="mdi-clock-outline"
                >
                  <v-card
                    :style="{
                      backgroundColor: 'rgba(255, 255, 255, 0.65)'
                    }"
                  >
                    <v-card-title
                      v-if="lineup.title"
                      v-html="lineup.title"
                    ></v-card-title>
                    <v-card-text
                      v-if="lineup.mdHtml"
                      v-html="lineup.mdHtml"
                      class="lineup-text"
                    ></v-card-text>
                  </v-card>
                </v-timeline-item>
              </v-timeline>
              <h3 class="mt-3">イベント詳細</h3>
              <p class="mt-3">
                <span class="font-weight-bold">開催日</span>:
                2024年8月17日 13:00 〜 17:00
              </p>
              <p class="mt-3">
                <span class="font-weight-bold">イベントURL</span>:
                <a
                  href="https://wbawakate.connpass.com/event/325229/"
                  target="_blank"
                  >https://wbawakate.connpass.com/event/325229/</a
                >
              </p>
              <div v-html="appendixHtml" class="appendix-text"></div>
            </div>
          </v-card-text>
          <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn
              class="ma-3"
              variant="outlined"
              size="x-large"
              color="primary"
              prepend-icon="mdi-calendar"
              text="イベント参加"
              href="https://wbawakate.connpass.com/event/325229/"
              target="_blank"
            ></v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<style>
.lineup-text h4 {
  font-size: 1.2em;
  margin-top: 1em;
}

.lineup-text h4 + p {
  margin-top: 0.5em;
}

.appendix-text h3 {
  font-size: 1.5em;
  margin-top: 1em;
}

.appendix-text h3 + p {
  margin-top: 1em;
}
</style>