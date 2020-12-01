<template>
<v-container>
  <v-row>
    <v-col class="text-center">
      Profile
    </v-col>
  </v-row>
  <v-row justify="center">
    <v-col cols="12" lg="3">image</v-col>
    <v-col cols="12" lg="3">
      <v-row>
        <v-col cols="12">
          Name: Erika Nicole Winters
        </v-col>
        <v-col  cols="12">Location: Looking to relocate!</v-col>
        <v-col cols="12">Hobbies: </v-col>
      </v-row>
    </v-col>
  </v-row>
  <v-row class="text-center">
    <v-col>
      A little about me
    </v-col>
  </v-row>
  <v-row  v-for="(fact, f) in facts" :key="f" justify="center">
    <v-col cols="10" md="9" lg="7" xl="5">
      <v-card class="pa-2" tile outlined>
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
      facts: ["I spend a lot of time cooking food and looking for recipes from around the world","I lived abroad in Japan for a year on an island famous for flowers and onions","My favorite rpg class is mage","I love multimedia art and making decorative crafts and cards","My favorite music genres are synthpop and new wave"]
    })
  };
</script>

<style scoped>
</style>