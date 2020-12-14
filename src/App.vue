<template>
  <v-app app>
    <v-app-bar app inverted-scroll scroll-threshold="64" color="primary" dark>
      <v-container>
        <v-row class="text-center" justify="center">
          <v-spacer></v-spacer>
          <v-col sm="2">
            About Me
          </v-col>
          <v-col sm="2">
            My Resume
          </v-col>
          <v-col sm="2">
            Contact Me
          </v-col>
          <v-spacer></v-spacer>
        </v-row>
      </v-container>
    </v-app-bar>

    <v-main class="bg">
      <v-container fluid class=" pt-0 text-center">
        <v-row justify="center">
          <v-col lg="7">
            <v-img class="white--text align-end" src="./assets/galax.png">
              <v-row>
                <v-col>
                  <span class="text-h1 font-weight-bold"
                    >I'm Erika N Winters</span
                  >
                </v-col>
              </v-row>
              <v-row>
                <v-col>
                  <span class="text-h3 font-weight-medium"
                    >I'm a developer and designer</span
                  >
                </v-col>
              </v-row>
            </v-img>
          </v-col>
        </v-row>
        <v-row>
          <v-col id="menuscroll">
            blaHSDKJHDDS ;KJHEHJFNSDJKHFL HLKJWHDELKJSAHDLKSJA
          </v-col>
        </v-row>
      </v-container>
      <v-container fluid>
        <v-row>
          <v-col></v-col>
          <v-col cols="10" md="9" lg="7">
            <v-container fluid>
              <v-row>
                <v-col>
                  <Resume />
                </v-col>
              </v-row>
              <v-row>
                <v-col>
                  <Projects />
                </v-col>
              </v-row>
              <v-row>
                <v-col> <About /></v-col
              ></v-row> </v-container
          ></v-col>
          <v-col class="bg"></v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import About from "./components/About";
import Resume from "./components/Resume";
import Projects from "./components/Projects";

export default {
  name: "App",

  components: {
    Resume,
    About,
    Projects,
  },

  data: () => ({
    //
  }),
};
</script>

<style>
.bg {
  background-color: black;
}

.mainbg {
  background-color: #fafafa;
}

.gradienttext {
  background: linear-gradient(to right, #ccffff, #ccccff);
  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
</style>
