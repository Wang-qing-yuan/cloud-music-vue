<template>
  <div>
    <template>
      <v-row justify="space-around">
        <v-col cols="12" sm="18" md="15" lg="30">
          <v-sheet elevation="10" class="pa-4 gut" style="padding:15px">
            <div class="gutter">
              <span>
                <mu-text-field v-model="keywords" placeholder="输入关键词搜索" class="search"></mu-text-field>
                <v-btn icon @click="search()">
                  <v-icon>mdi-magnify</v-icon>
                </v-btn>
              </span>
            </div>
            <v-chip v-for="(type, index) in types" :key="index" :value="index" @click="showList(index)">{{ type.type }}</v-chip>
          </v-sheet>
        </v-col>
      </v-row>
    </template>
    <mu-row v-if="show">
      <mu-col span="6" v-for="(child, index) in types[typeId].child" :key="index">
        <div class="grid-cell">
          <template>
            <v-card class="mx-auto grid">
              <v-img class="tu" :src="child.thumbnail"></v-img>

              <div class="title">
                <v-card-subtitle class="pb-0"
                  ><h3>{{ child.song_list_name }}</h3></v-card-subtitle
                >

                <v-card-text class="text--primary">
                  <h4>歌曲数：{{ child.song_count }}</h4>

                  <h4>收藏数：{{ child.like_count }}</h4>
                </v-card-text>
                <div class="btn">
                  <v-btn class="mx-2 magrin" fab dark small color="primary">
                    <v-icon dark>mdi-minus</v-icon>
                  </v-btn>
                  <v-btn class="mx-2 magrin" fab dark small color="indigo">
                    <v-icon dark>mdi-plus</v-icon>
                  </v-btn>
                  <v-btn class="mx-2 magrin" fab dark small color="pink">
                    <v-icon dark>mdi-heart</v-icon>
                  </v-btn>

                  <v-btn class="mx-2 magrin" fab dark small color="cyan">
                    <v-icon dark>mdi-pencil</v-icon>
                  </v-btn>
                </div>
              </div>
            </v-card>
          </template>
        </div>
      </mu-col>
    </mu-row>
    <mu-row v-else>
      <!-- <mu-col span="5" v-for="(item, index) in songList" :key="index">
        <div class="grid-cell">
          <template>
            <v-card class="mx-auto" max-width="400">
              <v-img class="white--text align-end" height="200px" :src="item.thumbnail"></v-img>

              <v-card-subtitle class="pb-0 h">{{ item.songListName }}</v-card-subtitle>

              <v-card-text class="text--primary">
                <div>歌曲数：{{ item.songCount }}</div>

                <div>收藏数：{{ item.likeCount }}</div>
              </v-card-text>

              <v-card-actions>
                <v-btn color="green" text>Enter</v-btn>

                <v-btn color="orange" text>Explore</v-btn>

                <v-btn color="red" text>Delete</v-btn>
              </v-card-actions>
            </v-card>
          </template>
        </div>
      </mu-col> -->
      <mu-col span="6" v-for="(item, index) in songList" :key="index">
        <div class="grid-cell">
          <template>
            <v-card class="mx-auto grid">
              <v-img class="tu" :src="item.thumbnail"></v-img>

              <div class="title">
                <v-card-subtitle class="pb-0"
                  ><h3>{{ item.songListName }}</h3></v-card-subtitle
                >

                <v-card-text class="text--primary">
                  <h4>歌曲数：{{ item.songCount }}</h4>

                  <h4>收藏数：{{ item.likeCount }}</h4>
                </v-card-text>
                <div class="btn">
                  <v-btn class="mx-2 magrin" fab dark small color="primary">
                    <v-icon dark>mdi-minus</v-icon>
                  </v-btn>
                  <v-btn class="mx-2 magrin" fab dark small color="indigo">
                    <v-icon dark>mdi-plus</v-icon>
                  </v-btn>
                  <v-btn class="mx-2 magrin" fab dark small color="pink">
                    <v-icon dark>mdi-heart</v-icon>
                  </v-btn>

                  <v-btn class="mx-2 magrin" fab dark small color="cyan">
                    <v-icon dark>mdi-pencil</v-icon>
                  </v-btn>
                </div>
              </div>
            </v-card>
          </template>
        </div>
      </mu-col>
    </mu-row>
  </div>
</template>

<script>
export default {
  name: 'MusicType',
  data() {
    return {
      selected: [],
      menus: [],
      types: [],
      typeId: 0,
      songList: [],
      keywords: '',
      show: true
    }
  },
  created() {
    //获取所有歌曲
    this.axios.get(this.GLOBAL.baseUrl + '/songList/type').then((res) => {
      this.types = res.data.data
      console.log(this.types)
    })
  },
  methods: {
    showList(Id) {
      this.show = !this.show
      this.typeId = Id
    },
    //模糊查询歌单
    search() {
      this.axios({
        method: 'get',
        url: this.GLOBAL.baseUrl + '/songList/select',
        // 问号带参，表单提交
        params: {
          field: this.keywords
        }
      }).then((res) => {
        this.songList = res.data.data
      })
      this.show = !this.show
    }
  }
}
</script>

<style scoped lang="scss">
// .tui {
//   color: #1a1a1a;
//   font-size: 18px;
//   line-height: 28px;
//   max-height: 56px;
//   font-weight: 600;
//   margin-left: 5px;
// }
.grid {
  background-image: linear-gradient(to top right, rgb(170, 171, 212), rgb(200, 167, 195), rgb(53, 56, 103));
  margin: 20px;
  border-radius: 20px;
  height: 200px;
  padding: 20px;
}
.gut {
  background-color: rgb(227, 222, 222);
}
.search {
  width: 90%;
}
.tu {
  height: 130px;
  width: 130px;
  border-radius: 20px;
}
h1,
h2,
h3,
h4,
h5,
h6,
p,
span {
  color: white;
}
.title {
  position: relative;
  top: -130px;
  left: 120px;
}
.btn {
  position: relative;
  top: 20px;
  right: 120px;
}
.magrin {
  margin-right: 20px;
}
</style>
