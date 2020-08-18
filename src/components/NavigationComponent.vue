<template>
<div>
    <v-app-bar
      app
      color="red darken-4"
      dense
      dark
      collapse-on-scroll
    >
      <v-toolbar-title>Library Management</v-toolbar-title>

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
          <v-tabs>
            <v-tab to="/">Home</v-tab>
            <v-tab to="/about">About</v-tab>
          </v-tabs>
        </template>
    </v-app-bar>
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