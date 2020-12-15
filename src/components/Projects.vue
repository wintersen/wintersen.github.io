<template>
  <v-container fluid>
    <v-row>
      <v-col class="text-center text-h3  font-weight-bold mb-5 gradienttext">
        My Projects
      </v-col>
    </v-row>

    <v-row align="stretch" justify="space-around">
      <v-col
        v-for="(project, i) in projects"
        :key="i"
        cols="12"
        sm="8"
        md="6"
        lg="4"
        class="px-5"
        ><v-hover v-slot:default="{ hover }">
          <v-card
            color="black"
            width="100%"
            class="white--text d-flex flex-column gradborder rounded-0"
          >
            <v-img height="150" :src="require(`../assets/${project.image}`)">
              <v-expand-transition>
                <div
                  v-if="hover"
                  class="d-flex transition-fast-in-fast-out orange darken-2 v-card--reveal display-3 white--text"
                  style="height: 100%;"
                ></div> </v-expand-transition
            ></v-img>

            <span class="text-h5 pa-5 pb-0">{{ project.title }}</span>
            <span class="pa-5 pb-3 pt-0 purple--text text--accent-2">{{
              project.type
            }}</span>

            <div class="px-5" style="min-height: 180px">
              <p>{{ project.description }}</p>
            </div>

            <v-btn
              v-ripple="{ class: 'warning--text' }"
              class="rounded-0"
              color="purple darken-1 white--text"
              :href="project.link"
              target="_blank"
              block
            >
              See Project
            </v-btn>
          </v-card></v-hover
        >
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "Projects",
  data: () => ({
    projects: [
      {
        title: "The Art of Experience",
        type: "Honors Thesis",
        description:
          "My thesis, focusing on the concept the perception of differences between virtual and traditional art.  I used Vuforia and Google Cardboard to develop AR and VR artpieces, and created a full installation for patrons.",
        image: "taoe.jpg",
        link:
          "https://www.arcgis.com/apps/Cascade/index.html?appid=c51cdcef71d14051b04665cc3d3cefcd",
      },
      {
        title: "The Hole Moon",
        type: "Game Jam",
        description:
          "My entry for Brackey's Game Jam 2020.1, which placed #23 for Graphics and #157 Overall out of 723 submissions.  Made with Unity2D and programmed in C# in three days.",
        image: "thm.png",
        link: "https://xokolade.itch.io/the-hole-moon",
      },
      {
        title: "Dynamic Memory",
        type: "Independent Study",
        description:
          "I was tasked to mimic a professional game development cycle with deliverables, a canban, sprint meetings, and design document.  Made with Unity2D and programmed in C#.",
        image: "dm.jpg",
        link:
          "https://drive.google.com/drive/folders/1wqy3emKkaVAAI0R_HIKXomNNBuTzTyW9?usp=sharing",
      },
    ],
  }),
};
</script>

<style scoped>
.gradborder {
  border: 1px solid;
  border-image: linear-gradient(90deg, #663399, #000066) 1;
}

.v-btn::before {
  background-color: #e91e63;
}

.v-card--reveal {
  opacity: 0.25;
  position: absolute;
  width: 100%;
}
</style>
