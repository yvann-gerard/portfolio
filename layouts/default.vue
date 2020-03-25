<template>
  <v-app dark>
    <v-navigation-drawer :mini-variant="miniVariant" fixed app width="200px" permanent style="background-color: #333333">
      <v-img v-if="!miniVariant" :src="profilePic" height="150" width="150" style="margin-left: 11%; margin-top: 11%; border-radius: 50%; border: 2px solid orange;" ></v-img>
      <v-toolbar-title v-if="!miniVariant" style="margin-left: 17%; margin-top: 20px">Yvann Gerard</v-toolbar-title>
      <v-list style="margin-top: 20px">
        <v-list-tile v-for="(item, i) in items" :key="i" :to="item.to" router exact style="margin-top: 20px">
          <v-list-tile-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title v-text="item.title" />
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar :clipped-left="clipped" fixed app height="50px" style="background-color: #777777">
      <v-btn icon @click.stop="miniVariant = !miniVariant">
        <v-icon>{{ `chevron_${miniVariant ? 'right' : 'left'}` }}</v-icon>
      </v-btn>
      <v-toolbar-title v-text="title"/>
      <v-spacer/>
      <a :href="this.$route.fullPath.substring(0,this.$route.fullPath.indexOf('?')) + '?lng=en'">
        <div v-bind:class="{ 'active-flag': language == 'en', 'flag': language != 'en'}">
          <v-img :src="flags.british" />
        </div>
      </a>
      <a :href="this.$route.fullPath.substring(0,this.$route.fullPath.indexOf('?')) + '?lng=fr'">
        <div v-bind:class="{ 'active-flag': language == 'fr', 'flag': language != 'fr'}">
          <v-img :src="flags.french"/>
        </div>
      </a>
    </v-toolbar>
    <v-content style="background-color: #e8e8e3">
      <v-container>
        <nuxt/>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
export default {
  watch: {
    $route(route) {
      if (route.name == "index") this.title = "Profile";
      else
        this.title = route.name.charAt(0).toUpperCase() + route.name.slice(1);
    }
  },
  mounted() {
    this.language = this.$route.query.lng;
    this.$i18n.locale = this.$route.query.lng;
    if (this.$route.name && this.$route.name != "index")
      this.title =
        this.$route.name.charAt(0).toUpperCase() + this.$route.name.slice(1);
  },
  methods: {
    changeLanguage(lang) {  
      this.$i18n.locale = lang;
    }
  },
  head () {
    return {
      link: [
        { rel: 'stylesheet', href: 'https://fonts.googleapis.com/css?family=Inconsolata&display=swap' }
      ]
    }
  },
  data() {
    return {
      language:"en",
      clipped: false,
      items: [
        {
          icon: "person",
          title: "Profile",
          to: "/?lng=" + this.$i18n.locale
        },
        {
          icon: "videogame_asset",
          title: "Projects",
          to: "/projects?lng=" + this.$i18n.locale
        },
        {
          icon: "school",
          title: "Curriculum Vitae",
          to: "/cv"
        }
      ],
      flags: {
        french: require('../assets/images/France.svg'),
        british: require('../assets/images/United_Kingdom.svg'),
      },
      profilePic: require('../assets/images/ProfilePic.jpg'),
      miniVariant: false,
      title: "Profile"
    };
  }
};
</script>

<style scoped>
  template {
    font-family: Inconsolata, sans-serif !important;
  }

  .active-flag{
    width: 40px; 
    height: 21px; 
    margin-left: 20px;
    border-style: solid;
    border-color: orange;
    border-width: 1px;
  }

  .flag{
    width: 40px; 
    height: 20px; 
    margin-left: 20px;
    border-style: none;
  }

  .v-navigation-drawer > .v-list .v-list__tile--active .v-list__tile__title,
  .v-list__tile--active .v-list__tile__action:first-of-type .v-icon
  {
    color: orange !important;
  }
</style>
