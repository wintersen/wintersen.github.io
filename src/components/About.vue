<template>
<v-container fluid>
  <v-row>
    <v-col class="text-center text-h3  font-weight-bold mb-5 gradienttext">
      About Me
    </v-col>
  </v-row>
  <v-row justify="center">
    <v-col cols="12" md="9" lg="9">
      <v-img src="../assets/selfportrait.png" aspect-ratio="1" max-height="500" contain></v-img>
    </v-col>
  </v-row>
  <v-row class="text-center my-5" justify="center">
    <v-col cols="12" md="9" lg="7" >
      <p class="white--text">Ever since I was a kid, I've been a stickler for detail and a creative soul. 
      Though I chose to study computer science in university, I have passion for both technology and art equally and strive to incorporate both in my life. 
      I like being challenged and adapting to new environments.  I also love playing games, especially strategy.</p>
    </v-col>
  </v-row>
  <v-row  v-for="(fact, f) in facts" :key="f" justify="center">
    <v-col cols="12" md="9" lg="8">
      <v-card class="white--text pa-2 pl-5 text-h5" color="black gradborder"  >
        {{fact}}
      </v-card>
    </v-col>
  </v-row>
</v-container>
</template>

<script>
  export default {
    name: "About",
    data: () =>({
      facts: ["I spend a lot of time cooking food and looking for recipes from around the world 🍱",
      "I lived abroad in Japan for a year on an island famous for flowers and onions 🌸",
      "My favorite rpg class is mage 🔮",
      "I love multimedia art and making crafts and cards ✂️",
      "My favorite music genres are synthpop and new wave 🎵",
      "There is always room for dessert 🍰"]
    })
  };
</script>

<style scoped>

.gradborder {
  border-left: 1px solid;
  border-image: linear-gradient(180deg, #ff33cc, #ff33cc) 1;
}
</style>