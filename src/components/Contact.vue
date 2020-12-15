<template>
  <v-container class="white--text text-h5 text-center" fluid>
    <v-row>
      <v-col class="text-center text-h3  font-weight-bold mb-5 gradienttext">
        Contact Me
      </v-col>
    </v-row>
    <v-row>
      <v-col
        ><a class="anav" :href="`${publicPath}ErikaWintersResume.pdf`" download
          >Grab a copy of my <span style="color: #3addea">resume</span></a
        ></v-col
      >
    </v-row>
    <v-row>
      <v-col>Mail me @ <span style="color: #ff6666">erikanwinters@gmail.com</span></v-col>
    </v-row>
    <v-row>
      <v-col>You can see me on</v-col>
    </v-row>
    <v-row justify="center">
      <v-col cols="1"
        ><a href="https://www.linkedin.com/in/winterse/" target="__blank"
          ><v-icon color="white" x-large>mdi-linkedin</v-icon></a
        ></v-col
      >
      <v-col cols="1"
        ><a href="https://github.com/wintersen" target="__blank"
          ><v-icon color="white" x-large>mdi-github</v-icon></a
        ></v-col
      >
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "Contact",
  data: () => ({
    publicPath: process.env.BASE_URL,
  }),
};
</script>
<style scoped>
a {
  text-decoration: none;
}
</style>
