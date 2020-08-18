<template>
  <v-app app>
   <NavigationComponent />
    <v-main>
        <v-container class="fill-height">
          <v-row align="center" justify="center">
              <router-view></router-view>
          </v-row>
        </v-container>
    </v-main>
  </v-app>
</template>

<script>
import NavigationComponent from "./components/NavigationComponent";

export default {
  name: "App",

  components: {
    NavigationComponent,
  },

  data: () => ({
    
  }),
};
</script>
