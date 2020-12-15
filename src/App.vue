<template>
  <v-app app>
    <v-app-bar
      app
      inverted-scroll
      scroll-threshold="64"
      color="black"
      dark
      class="gradbordernav"
    >
      <v-container>
        <v-row class="text-center" justify="center">
          <v-spacer></v-spacer>
          <v-col cols="4" sm="2">
            <a class="anav" href="#1">Resume</a>
          </v-col>
          <v-col cols="4" sm="2">
            <a class="anav" href="#2">About</a>
          </v-col>
          <v-col cols="4" sm="2">
            <a class="anav" href="#3">Contact</a>
          </v-col>
          <v-spacer></v-spacer>
        </v-row>
      </v-container>
    </v-app-bar>

    <v-main class="bg">
      <div class="starsgreen">
        <div class="starspurple">
          
            <v-container fluid class=" py-0 text-center">
              <v-row class="headerbg" justify="center">
                <v-col style="height:100vh">
                  <!-- this one for large screens -->

                  <v-img
                    class="white--text align-end hidden-md-and-down"
                    height="100vh"
                    contain
                    src="./assets/galax.png"
                  >
                    <v-row justify="center">
                      <v-col lg="7">
                        <span class="text-h3 text-sm-h1 font-weight-bold"
                          >I'm Erika N Winters</span
                        >
                      </v-col>
                    </v-row>
                    <v-row justify="center">
                      <v-col lg="7" class="pb-5">
                        <span
                          class="gradienttext text-h5 text-sm-h3 font-weight-medium"
                          >I'm a developer and designer</span
                        >
                      </v-col>
                    </v-row>
                  </v-img>
                  <!-- this one for small screens -->
                  <v-img
                    class="white--text align-end hidden-lg-and-up"
                    height="100vh"
                    src="./assets/galax.png"
                  >
                    <v-row justify="center">
                      <v-col lg="7">
                        <span class="text-h3 text-sm-h1 font-weight-bold"
                          >I'm Erika N Winters</span
                        >
                      </v-col>
                    </v-row>
                    <v-row justify="center">
                      <v-col lg="7" class="pb-5">
                        <span
                          class="gradienttext text-h5 text-sm-h3 font-weight-medium"
                          >I'm a developer and designer</span
                        >
                      </v-col>
                    </v-row>
                  </v-img>
                </v-col>
              </v-row>
            </v-container>
            <div class="bg2">
            <v-container fluid>
              <div style="height: 100px"></div>
              <v-row justify="center">
                <v-col cols="10" md="9" lg="6" class="white--text text-center blackbg">
                  <p class="mt-3">
                    In a competitive and fast-paced world, you need to be aware
                    of both the experience and the efficiency of the product
                    you're making. You need people who can see the big picture,
                    work well in a constantly changing environment, and are able
                    to adapt to new challenges quickly.
                  </p>
                  <p
                    class="text-h5 mt-5 font-weight-medium"
                    style="color: #ff6666"
                  >
                    I'm here to fulfill that need.
                  </p>
                  <p class="mt-5">
                    With equal experience working on web development and web
                    design, I'm confident in my ability to overcome any task and
                    work with any team. I take pride in the quality of my work,
                    and am well-known to be excellent at assessing client needs
                    and creating considerate solutions. Any project I work on I
                    dedicate my all to, and endeavor to make it better than the
                    best.
                  </p>
                  <p class="mt-3 text-decoration-underline">
                    Looking to relocate!
                  </p>
                </v-col>
              </v-row>
              <v-row>
                <v-col></v-col>
                <v-col cols="10" md="10" lg="9" xl="8">
                  <v-container fluid>
                    <div id="1" style="height:25px"></div>
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
                    <div id="2" style="height:25px"></div>
                    <v-row>
                      <v-col><About /></v-col>
                    </v-row>
                    <div id="3" style="height:25px"></div>
                    <v-row>
                      <v-col><Contact /></v-col
                    ></v-row>
                  </v-container>
                </v-col>
                <v-col></v-col>
              </v-row>
            </v-container>
          </div>
        </div>
      </div>
    </v-main>
  </v-app>
</template>

<script>
import About from "./components/About";
import Resume from "./components/Resume";
import Projects from "./components/Projects";
import Contact from "./components/Contact";

export default {
  name: "App",

  components: {
    Resume,
    About,
    Projects,
    Contact,
  },

  data: () => ({
    //
  }),
};
</script>

<style>
.v-card__text,
.v-card__title {
  word-break: normal; /* maybe !important  */
}

.blackbg{
  background-color: black;
}
.bg {
  background-image: url("./assets/bg3.jpg");

  background-repeat: repeat-y;
}
.bg2 {
  background-image: url("./assets/bg2.png");
  background-repeat: repeat;
  background-size: contain;

}
.headerbg {
  background-image: url("./assets/headerbg.png");
  background-size: cover;
}

.starsgreen {
  height: 100%;
  width: 100%;
  background: url("./assets/starsgreen.png") repeat 5% 5%;
  animation-name: STAR-MOVE;
  animation-duration: 1000s;
  animation-timing-function: linear;
  animation-iteration-count: infinite;
}
.starspurple {
  height: 100%;
  width: 100%;
  background: url("./assets/starspurple.png") repeat 5% 5%;

  animation-name: STAR-MOVE;
  animation-duration: 350s;
  animation-timing-function: linear;
  animation-iteration-count: infinite;
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

.gradbordernav {
  border-bottom: 1px solid;
  border-image: linear-gradient(45deg, #4bdde5, #090e43, #cc33cc) 1;
}

.anav {
  text-decoration: none;
  color: white !important;
}
.anav:hover {
  text-decoration: underline;
}

@keyframes STAR-MOVE {
  from {
    background-position: 0% 0%;
  }
  to {
    background-position: 300% 100%;
  }
}
</style>
