<template >
  <div style="margin-left: 10%">
    <v-layout column justify-center align-center style="background-color: #ffffff; width: 200%; margin-left: -30%; margin-top: -23px">
      <v-flex xs12 sm12 md12 style="width: 200%; margin-left : 20%; color: #000000">
        <v-card-title class="headline">{{$t("info")}}</v-card-title>
        <v-card-text>
          <p>{{$t("aboutDescription")}}</p>
        </v-card-text>
      </v-flex>
    </v-layout>
    <v-layout column justify-center align-center>
      <v-flex xs12 sm12 md12 style="margin-left: -20%; margin-top: 25px; width: 110%; color: #000000;">
          <v-card-title class="headline" style="text-align: center">{{$t("projects")}}</v-card-title>
          <v-card-text>
            <v-layout row wrap>
              <v-flex xs4>
                <v-tooltip bottom>
                  <template v-slot:activator="{ on }">
                    <a href="https://github.com/yvann-gerard/elements-isometric">
                      <v-img v-on="on" :src="images.first" height="250" width="250" style="margin-left: 30%; margin-top: 0px; border-radius: 50%; border: 2px solid orange;"></v-img>
                    </a>
                  </template>
                  <span>{{$t("tooltipProject")}}</span>
                </v-tooltip>
              </v-flex>
              <v-flex xs4>
                <v-tooltip bottom>
                  <template v-slot:activator="{ on }">
                    <a href="https://github.com/yvann-gerard/towering-light">
                      <v-img v-on="on" :src="images.second" height="250" width="250" style="margin-left: 30%; margin-top: 0px; border-radius: 50%; border: 2px solid orange;"></v-img>
                    </a>
                  </template>
                  <span>{{$t("tooltipProject")}}</span>
                </v-tooltip>
              </v-flex>
              <v-flex xs4>
                <v-tooltip bottom>
                  <template v-slot:activator="{ on }">
                    <a href="https://github.com/yvann-gerard/population">
                      <v-img v-on="on" :src="images.third" height="250" width="250" style="margin-left: 30%; margin-top: 0px; border-radius: 50%; border: 2px solid orange;"></v-img>
                    </a>
                  </template>
                  <span>{{$t("tooltipProject")}}</span>
                </v-tooltip>
              </v-flex>
            </v-layout>
            <v-layout row wrap style="margin-top: 50px">
              <v-flex xs4>
                <v-tooltip bottom>
                  <template v-slot:activator="{ on }">
                    <a href="https://github.com/yvann-gerard/pathfinding">
                      <v-img v-on="on" :src="images.fourth" height="250" width="250" style="margin-left: 30%; margin-top: 0px; border-radius: 50%; border: 2px solid orange;"></v-img>
                    </a>
                  </template>
                  <span>{{$t("tooltipProject")}}</span>
                </v-tooltip>
              </v-flex>
              <v-flex xs4>
                <v-tooltip bottom>
                  <template v-slot:activator="{ on }">
                    <a href="https://github.com/yvann-gerard/sun-wind-map">
                      <v-img v-on="on" :src="images.fifth" height="250" width="250" style="margin-left: 30%; margin-top: 0px; border-radius: 50%; border: 2px solid orange;"></v-img>
                    </a>
                  </template>
                  <span>{{$t("tooltipProject")}}</span>
                </v-tooltip>
              </v-flex>
              <v-flex xs4>
                <v-img v-on="on" :src="images.sixth" height="250" width="250" style="margin-left: 30%; margin-top: 0px; border-radius: 50%; border: 3px solid black;"></v-img>
              </v-flex>
            </v-layout>
          </v-card-text>
      </v-flex>
    </v-layout>
    <v-layout column justify-center align-center style="background-color: #ffffff; width: 200%; margin-left: -30%; margin-top: 23px; margin-bottom: -23px">
      <v-flex xs12 sm12 md12 style="width: 200%; margin-left : 20%; color: #000000">
        <v-card-title class="headline">Coding challenges</v-card-title>
        <v-card-text>
          <p>{{$t("challengesPreLink")}} <a href="https://www.codewars.com/users/yvann-gerard">CodeWars</a>{{$t("challengesPostLink")}}</p>
            <v-img v-if="this.$route.query.lng=='fr'" :src="images.challengesFr" height="300" contain style="margin-left: -50%"></v-img>
            <v-img v-if="this.$route.query.lng!='fr'" :src="images.challengesEn" height="300" contain style="margin-left: -50%"></v-img>
        </v-card-text>
      </v-flex>
    </v-layout>
  </div>
</template>


<script>
import Logo from "~/components/Logo.vue";
import VuetifyLogo from "~/components/VuetifyLogo.vue";

export default {
  components: {
    Logo,
    VuetifyLogo
  },
  data() {
    return {
      on: false,
      images: {
        first: require('../assets/images/1.png'),
        second: require('../assets/images/2.png'),
        third: require('../assets/images/3.png'),
        fourth: require('../assets/images/4.png'),
        fifth: require('../assets/images/5.png'),
        sixth: require('../assets/images/6.png'),
        challengesFr: require('../assets/images/ChallengesFr.png'),
        challengesEn: require('../assets/images/ChallengesEn.png'),
      }
    }
  }
};
</script>

<style scoped>
  p{
    white-space: pre-line;
  }
</style>