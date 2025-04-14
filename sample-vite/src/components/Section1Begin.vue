<script setup>
const basePath = '.'

const contentLi = {
  ttl: '全脳アーキテクチャ若手の会の10年間を振り返る (サンプル版)',
  subTtl: 'WBA若手10周年記念「AIの10年間を振り返る」イベント開催特別企画',
  desc: `全脳アーキテクチャ若手の会 (WBA若手) は、たった10分のプレゼンテーションから始まりました。
ドラえもんや鉄腕アトムを見ながら育った私たちの手で、彼らのような人工知能を創りたい。

もし彼らのような人工知能を創れるとすれば、私たちの世代かもしれない。

だからこそ今から私たちの世代がネットワークを広げ、お互いに刺激しあい、
継続して協力し合うことで、これからさらに10年後の日本を人工知能大国にしたい。

この時の私の主張はこんなところでした。その想いは私の想像をはるかに超えて、
多くの人に賛同していただき、この全脳アーキテクチャ若手の会を立ち上げることができました。
2024年7月現在、Facebookグループでは2500人を超える方々に参加していただいています。

それでは、全脳アーキテクチャ若手の会がAIとともに歩んだ10年間を振り返ってみましょう。`,
}
</script>

<template>
  <v-container
    class="ma-0 pa-0 w-100"
    :style="{ position: 'relative', maxWidth: '100%', minHeight: '100vh' }"
  >
    <!-- SP -->
    <div class="d-md-none">
      <v-parallax
        class="d-flex align-center bg-white w-100"
        :src="basePath + '/img/cover.jpg'"
        min-height="100vh"
        height="100%"
      >
        <div
          :style="{
            position: 'absolute',
            left: 0,
            top: 0,
            width: '100%',
            height: '100%',
            background: `linear-gradient(
              to right,
              rgba(255, 255, 255, .65) 65%,
              rgba(255, 255, 255, .25) 100%
            )`,
          }"
        ></div>
        <v-sheet
          class="bg-transparent pa-15"
          :style="{ position: 'relative' }"
        >
          <h3 class="text-h6 mb-3">{{ contentLi.subTtl }}</h3>
          <h2 class="text-h5 mb-3">{{ contentLi.ttl }}</h2>
          <p
            v-for="line in contentLi.desc.split('\n\n')"
            class="mt-3 text-body-1"
            v-html="line.split('\n').join('<br>')"
          ></p>
          <p class="mt-6 font-weight-bold">
            <span class="mr-3">全脳アーキテクチャ若手の会 創設者</span>
            <span>大澤正彦</span>
          </p>
          <p class="mt-6">
            ※サンプル版では画像と文章を一部差し替えています。
          </p>
        </v-sheet>
      </v-parallax>
    </div>
    <!-- PC -->
    <div class="d-none d-md-block">
      <v-parallax
        class="d-flex align-center bg-white w-100"
        :src="basePath + '/img/cover.jpg'"
        min-height="100vh"
        height="100vh"
      >
        <div
          :style="{
            position: 'absolute',
            left: 0,
            top: 0,
            width: '100%',
            height: '100%',
            background: `linear-gradient(
              to right,
              rgba(255, 255, 255, .65) 65%,
              rgba(255, 255, 255, .25) 100%
            )`,
          }"
        ></div>
        <v-sheet
          class="bg-transparent pa-15"
          :style="{ position: 'relative' }"
        >
          <h3 class="text-h5 mb-6">{{ contentLi.subTtl }}</h3>
          <h2 class="text-h3 mb-6">{{ contentLi.ttl }}</h2>
          <p
            v-for="line in contentLi.desc.split('\n\n')"
            class="mt-3"
            v-html="line.split('\n').join('<br>')"
          ></p>
          <p class="mt-6 font-weight-bold">
            <span class="mr-3">全脳アーキテクチャ若手の会 創設者</span>
            <span>大澤正彦</span>
          </p>
          <p class="mt-6">
            ※サンプル版では画像と文章を一部差し替えています。
          </p>
        </v-sheet>
      </v-parallax>
    </div>
  </v-container>
</template>
