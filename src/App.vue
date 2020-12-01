<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <v-container>
        <v-row class="text-center" :justify="center">
          <v-spacer></v-spacer>
          <v-col sm="2">
            About Me
          </v-col>
          <v-col sm="2">
            My Experience
          </v-col>
          <v-col sm="2">
            Contact Me
          </v-col>
          <v-spacer></v-spacer>
        </v-row>
      </v-container>
    </v-app-bar>

    <v-main>
      <v-container class="text-center">
        <v-row>
          <v-col>
            image
          </v-col>
        </v-row>
        <v-row>
          <v-col>
            Hi, I'm Erika N Winters
          </v-col>
        </v-row>
        <v-row>
          <v-col>
            I'm a web developer and designer
          </v-col>
        </v-row>
      </v-container>
      <About/>>
      <Resume />
    </v-main>
  </v-app>
</template>

<script>
import About from "./components/About";
import Resume from "./components/Resume";

export default {
  name: "App",

  components: {
    Resume,
    About
  },

  data: () => ({
    //
  }),
};
</script>
