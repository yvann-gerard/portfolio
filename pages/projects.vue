<template>
  <v-layout column justify-center align-center>
    <v-flex xs12 sm12 md12 style="width: 80%; width: 100%; color: #000000;">
      <div class="whiteDivision" style="margin-top: -23px;">
        <v-card-title class="headline">{{$t("games")}}</v-card-title>
        <v-card-text>
          <p>{{$t("aboutGames")}}</p>
        </v-card-text>
      </div>
      <div class="greyDivision">
        <v-card-title class="headline">Elements Isometric</v-card-title>
        <v-card-text>
          <p>{{$t("aboutElement")}}</p>
          <a href="https://github.com/yvann-gerard/elements-isometric">https://github.com/yvann-gerard/elements-isometric</a>
          <v-img :src="images.first" height="250"></v-img>
        </v-card-text>
      </div>
      <div class="whiteDivision">
        <v-card-title class="headline">Towering light</v-card-title>
        <v-card-text>
          <p>{{$t("aboutTower")}}</p>
          <a href="https://github.com/yvann-gerard/towering-light">https://github.com/yvann-gerard/towering-light</a>
          <v-img :src="images.second" height="250"></v-img>
        </v-card-text>
      </div>
      <div class="greyDivision">
        <v-card-title class="headline">Population</v-card-title>
        <v-card-text>
          <p>{{$t("aboutPopulation")}}</p>
          <a href="https://github.com/yvann-gerard/population">https://github.com/yvann-gerard/population</a>
          <v-img :src="images.third" height="250"></v-img>
        </v-card-text>
      </div>
      <div class="whiteDivision">
        <v-card-title class="headline">Pathfinding</v-card-title>
        <v-card-text>
          <p>{{$t("aboutPathfinding")}}</p>
          <a href="https://github.com/yvann-gerard/pathfinding">https://github.com/yvann-gerard/pathfinding</a>
          <v-img :src="images.fourth" height="250"></v-img>
        </v-card-text>
      </div>
      <div class="greyDivision">
        <v-card-title class="headline">Projection</v-card-title>
        <v-card-text>
          <p>{{$t("aboutProjection")}}</p>
          <a href="https://github.com/yvann-gerard/sun-wind-map">https://github.com/yvann-gerard/sun-wind-map</a>
          <v-img :src="images.fifth" height="250"></v-img>
        </v-card-text>
      </div>
      <div class="whiteDivision">
        <v-card-title class="headline">Raspberry</v-card-title>
        <v-card-text>
          <p>{{$t("aboutRaspberry")}}</p>
          <v-img :src="images.sixth" height="250"></v-img>
        </v-card-text>
      </div>
    </v-flex>
  </v-layout>
</template>

<script>
export default {
  data() {
    return {
      images: {
        first: require('../assets/images/1.png'),
        second: require('../assets/images/2.png'),
        third: require('../assets/images/3.png'),
        fourth: require('../assets/images/4.png'),
        fifth: require('../assets/images/5.png'),
        sixth: require('../assets/images/6.png')
      }
    }
  }
};
</script>

<style scoped>
  p{
    white-space: pre-line;
  }

  .v-card{
    margin-top: 20px;
  }

  .greyDivision{
    margin-left: -30%; 
    width: 140%;
    padding-left: 30%; 
    padding-right: 10%;
  }

  .whiteDivision{
    margin-left: -30%; 
    width: 140%;
    padding-left: 30%; 
    padding-right: 10%;
    background-color: white;
  }
</style>