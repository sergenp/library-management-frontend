<template>
  <v-app>
   <NavigationComponent />
    <v-main>
        <v-container class="fill-height">
          <v-row align="center" justify="center">
            <HelloWorld/>
          </v-row>
        </v-container>
    </v-main>
  </v-app>
</template>

<script>
import NavigationComponent from "./components/NavigationComponent";
import HelloWorld from "./components/HelloWorld";

export default {
  name: "App",

  components: {
    NavigationComponent,
    HelloWorld
  },

  data: () => ({
    
  }),
};
</script>
