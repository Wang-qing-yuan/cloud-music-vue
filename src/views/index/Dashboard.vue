<template>
  <div>
    <template>
      <v-card class="mt-4 mx-auto aa">
        <v-sheet class="v-sheet--offset mx-auto" color="pink" elevation="12" max-width="calc(100% - 32px)">
          <v-sparkline :labels="labels" :value="value" color="white" line-width="2" padding="16"></v-sparkline>
        </v-sheet>

        <v-card-text class="pt-0">
          <div class="title font-weight-light mb-2">User increment</div>
          <div class="subheading font-weight-light grey--text">Last month performance</div>
          <v-divider class="my-2"></v-divider>
          <v-icon class="mr-2" small>
            mdi-clock
          </v-icon>
          <span class="caption grey--text font-weight-light">last registration 26 minutes ago</span>
        </v-card-text>
      </v-card>
    </template>

    <template>
      <v-card class="mt-4 mx-auto aa">
        <v-sheet class="v-sheet--offset mx-auto" color="pink" elevation="12" max-width="calc(100% - 32px)">
          <v-sparkline :labels="labels" :value="value" color="white" line-width="2" padding="16"></v-sparkline>
        </v-sheet>

        <v-card-text class="pt-0">
          <div class="title font-weight-light mb-2">Song downloads</div>
          <div class="subheading font-weight-light grey--text">Last month performance</div>
          <v-divider class="my-2"></v-divider>
          <v-icon class="mr-2" small>
            mdi-clock
          </v-icon>
          <span class="caption grey--text font-weight-light">last registration 26 minutes ago</span>
        </v-card-text>
      </v-card>
    </template>
  </div>
</template>

<script>
export default {
  name: 'Dashboard',
  data: () => ({
    labels: ['12k', '3k', '6k', '9k', '12k', '3k', '6k', '9k'],
    value: [200, 675, 410, 390, 310, 460, 250, 240],
    show: false
  })
}
</script>

<style scoped lang="scss">
.text {
  text-align: center;
  position: relative;
  top: 60px;
  right: 60px;
  color: white;
  font-weight: 900;
}
.aa {
 margin: 50px;
}
.v-sheet--offset {
  top: -24px;
  position: relative;
}
</style>
