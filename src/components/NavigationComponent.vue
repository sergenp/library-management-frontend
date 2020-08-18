<template>
<div>
    <v-app-bar
      app
      color="red darken-4"
      dense
      dark
      collapse-on-scroll
    >
      <v-app-bar-nav-icon @click="drawer = true">
          
      </v-app-bar-nav-icon>

      <v-toolbar-title>Library</v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-heart</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>

      <v-menu
        left
        bottom
      >
        <template v-slot:activator="{ on, attrs }">
          <v-btn
            icon
            v-bind="attrs"
            v-on="on"
          >
            <v-icon>mdi-dots-vertical</v-icon>
          </v-btn>
        </template>

        <v-list>
          <v-btn icon v-on:click="toggle_dark_mode">
              <v-icon>mdi-theme-light-dark</v-icon>
          </v-btn>
        </v-list>
      </v-menu>
        <template v-slot:extension>
          <v-tabs align-with-title>
            <v-tab to="/">Home</v-tab>
            <v-tab to="/about">About</v-tab>
          </v-tabs>
        </template>
    </v-app-bar>
    <v-navigation-drawer
      v-model="drawer"
      absolute
      temporary
    >
      <v-list-item>
        <v-list-item-avatar>
          <v-img :src="require('../assets/library.png')"></v-img>
        </v-list-item-avatar>

        <v-list-item-content>
          <v-list-item-title>Library</v-list-item-title>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list>
        <v-list-item
          v-for="item in items"
          :key="item.title"
          :to="item.link"
        >
          <v-list-item-icon>
            <v-icon>mdi-{{ item.icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
</div>
</template>

<script>
  export default {
    name : 'NavigationComponent',
    data () {
      return {
        drawer: null,
        items: [
          { title: 'Home', icon: 'home', link:'/' },
          { title: 'About', icon: 'progress-question', link:'/about' },
        ],
      }
    },
    methods: {
    toggle_dark_mode: function () {
        this.$vuetify.theme.dark = !this.$vuetify.theme.dark;
        localStorage.setItem("dark_theme", this.$vuetify.theme.dark.toString());
    }
  },
    mounted() {
      const theme = localStorage.getItem("dark_theme");
      if (theme) {
          if (theme == "true") {
              this.$vuetify.theme.dark = true;
          } else {
              this.$vuetify.theme.dark = false;
          }
      }
  },
  }
</script>