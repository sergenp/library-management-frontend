<template>
  <v-app app>
   <NavigationComponent />
    <v-main>
        <v-container>
          <router-view></router-view>
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
