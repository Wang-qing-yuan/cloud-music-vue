<template>
  <v-card class="mx-auto">
    <v-row class="aa">
      <v-col v-for="card in cards" :key="card.title" :cols="card.flex">
        <v-card class="aa">
          <v-img :src="card.src" :gradient="card.gradient" class="white--text align-end" height="200px">
            <v-card-title v-text="card.title" class="text"></v-card-title>
          </v-img>
        </v-card>
      </v-col>
    </v-row>
  </v-card>
</template>

<script>
export default {
  name: 'MusicList',
  data: () => ({
    cards: [
      {
        title: 'rock',
        src: 'https://lastfm.freetls.fastly.net/i/u/avatar170s/8c62d87f66134c779adfaf56a6b71cb4.webp',
        flex: 4,
        gradient: 'to bottom, rgba(0,0,0,0.5), rgba(0,0,0,0.5)'
      },
      {
        title: 'hip-hop',
        src: 'https://lastfm.freetls.fastly.net/i/u/avatar170s/f98e4d27438fbbef4290f31420eb1818.webp',
        flex: 4,
        gradient: 'to bottom, rgba(128,89,77,0.7), rgba(128,89,77,0.7)'
      },
      {
        title: 'indie',
        src: 'https://lastfm.freetls.fastly.net/i/u/avatar170s/d7cac7eb9f2eb696d13b3d9952cdb008.webp',
        flex: 4,
        gradient: 'to bottom, rgba(174,122,64,0.7), rgba(174,122,64,0.7)'
      },
      {
        title: 'jazz',
        src: 'https://lastfm.freetls.fastly.net/i/u/300x300/86f66b8fea6a12e7eacb06630069fa12.webp',
        flex: 4,
        gradient: 'to bottom, rgba(166,151,56,0.7), rgba(166,151,56,0.7)'
      },
      {
        title: 'reggae',
        src: 'https://lastfm.freetls.fastly.net/i/u/avatar300s/68eb0284a97fca41b9dfdc3b5da69af4.webp',
        flex: 4,
        gradient: 'to bottom, rgba(173,93,45,0.7), rgba(173,93,45,0.7)'
      },
      {
        title: 'british',
        src: 'https://lastfm.freetls.fastly.net/i/u/300x300/e235da19f6a169bd6dc2e021bcfbf674.webp',
        flex: 4,
        gradient: 'to bottom, rgba(161,136,121,0.7), rgba(161,136,121,0.7)'
      },
      {
        title: 'punk',
        src:
          'https://images.taboola.com/taboola/image/fetch/f_jpg%2Cq_auto%2Ch_334%2Cw_600%2Cc_fill%2Cg_faces:auto%2Ce_sharpen/http%3A//cdn.taboola.com/libtrc/static/thumbnails/7bf660bce66b93d235f82e666ed8f1bb.jpg',
        flex: 4,
        gradient: 'to bottom, rgba(137,49,53,0.7), rgba(137,49,53,0.7)'
      },
      {
        title: 'rnb',
        src: 'https://lastfm.freetls.fastly.net/i/u/300x300/63c9fb345299551722436ccb0b38ef55.webp',
        flex: 4,
        gradient: 'to bottom, rgba(0,0,0,0.5), rgba(0,0,0,0.5)'
      },
      {
        title: 'dance',
        src: 'https://lastfm.freetls.fastly.net/i/u/300x300/93b5eda0553bb81e467099709bd740f2.webp',
        flex: 4,
        gradient: 'to bottom, rgba(126,89,75,0.7), rgba(126,89,75,0.7)'
      },
      {
        title: '+',
        src:'https://us.123rf.com/450wm/weedezign/weedezign1507/weedezign150700028/42659982-%E3%82%BB%E3%83%A1%E3%83%B3%E3%83%88%E5%A3%81%E3%80%81%E3%83%86%E3%82%AF%E3%82%B9%E3%83%81%E3%83%A3%E8%83%8C%E6%99%AF%E3%81%AE%E7%99%BD%E8%89%B2%E5%A1%97%E6%96%99%E3%80%82.jpg?ver=6',
        flex: 4,
        gradient: 'to bottom, rgba(31,31,47,0.7), rgba(31,31,47,0.7)'
      }
    ],
    show: false
  })
}
</script>

<style scoped lang="scss">
.text {
  text-align: center;
  position: relative;
  top: 60px;
  right: 25px;
  color: white;
  font-weight: 900;
}
.aa{
  background-color: rgb(31,31,47);
}
</style>
