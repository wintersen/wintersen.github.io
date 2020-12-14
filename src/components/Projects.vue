<template>
  <v-container fluid>
    <v-row>
      <v-col class="text-center text-h3  font-weight-bold mb-5 gradienttext">
        My Projects
      </v-col>
    </v-row>

    <v-row v-for="(project, i) in projects" :key="i">
      <v-col>
        
      </v-col>
    </v-row>

    <v-row align="stretch" justify="space-around">
      <v-col
        v-for="(project, i) in projects"
        :key="i"
        cols="12"
        sm="6"
        md="6"
        lg="4"
        class="px-5"
      >
        <v-card width="75%" class="d-flex flex-column">
          <v-img
            height="150"
            :src="require(`../assets/${project.image}`)"
          ></v-img>

          <span class="text-h5 pa-5 pb-3">{{ project.title }}</span>

          <div class="px-5" style="min-height: 180px"><p>{{ project.description }}</p></div>

          <v-btn color="primary" :href="project.link" target="_blank" block>
            See Project
          </v-btn>
        </v-card>
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
        description:
          "My USF Honors College thesis project, focusing on the concept the perception of differences between virtual and traditional art.  I used Vuforia and Google Cardboard to develop AR and VR artpieces, and created a full installation for patrons.",
        image: "taoe.jpg",
        link: "https://www.arcgis.com/apps/Cascade/index.html?appid=c51cdcef71d14051b04665cc3d3cefcd",
      },
      {
        title: "The Hole Moon",
        description:
          "My entry for Brackey's Game Jam 2020.1, which placed #23 for Graphics and #157 Overall out of 723 submissions.  Made with Unity2D and programmed in C# in three days.",
        image: "thm.png",
        link: "https://xokolade.itch.io/the-hole-moon",
      },
      {
        title: "Dynamic Memory",
        description:
          "An independent study project for USF where I was tasked to mimic a professional game development cycle with deliverables, a canban, sprint meetings, and design document.  Made with Unity2D and programmed in C#.",
        image: "dm.jpg",
        link:
          "https://drive.google.com/drive/folders/1wqy3emKkaVAAI0R_HIKXomNNBuTzTyW9?usp=sharing",
      },
    ],
  }),
};
</script>
