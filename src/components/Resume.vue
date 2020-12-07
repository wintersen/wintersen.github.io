<template>
  <v-container>
    <v-row justify="center">
      <v-col></v-col>
      <v-col></v-col>
      <v-col></v-col>
    </v-row>
    <v-row justify="center">
      <v-col cols="12" md="1">
        <v-container  class="text-center">
          <v-row>
            <v-col md="12">
              <v-btn elevation="2" fab small color="pink" @click="showDev = !showDev"><v-icon color="white">mdi-code-braces-box</v-icon></v-btn>
            </v-col>
            <v-col md="12">
              <v-btn elevation="2" fab small color="blue" @click="showDes = !showDes"><v-icon color="white">mdi-gesture</v-icon></v-btn>
            </v-col>
            <v-col md="12">
              <v-btn elevation="2" fab small color="green" @click="showProj = !showProj"><v-icon color="white">mdi-monitor-dashboard</v-icon></v-btn>
            </v-col>
          </v-row>
        </v-container>
      </v-col>
      <v-col cols="12" md="10" lg="7">
        <v-timeline dense>
          <v-timeline-item
            v-for="(item, i) in orderedResume"
            :key="i"
            fill-dot
            :icon="getIcon(item.type)"
            v-show="getDisplay(item.type)"
          >
            <v-card>
              <v-card-title>
                {{ item.title }}
              </v-card-title>
              <v-card-subtitle class="pb-0">
                {{ item.where }} ~ {{ item.when }}
              </v-card-subtitle>
              <v-card-text>
                <v-container>
                  <v-row>
                    <v-col
                      class="pt-0"
                      v-for="(tool, t) in item.tools"
                      :key="t"
                      sm="2"
                      >{{ tool }}</v-col
                    >
                    <v-spacer></v-spacer>
                  </v-row>
                  <v-row>
                    <ul>
                      <li v-for="(rsp, r) in item.responsibilities" :key="r">
                        {{ rsp }}
                      </li>
                    </ul>
                  </v-row>
                </v-container>
              </v-card-text>
            </v-card>
          </v-timeline-item>
        </v-timeline>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "Resume",

  data: () => ({
    showDev: true,
    showDes: true,
    showProj: true,
    resumeItems: [
      {
        title: "Software Developer & Designer",
        where: "LeapCaller, LeapForward LLC, Tampa FL",
        start: new Date(2020, 7, 1),
        when: "Jul 2018 - Mar 2020",
        tools: ["JavaScript", "Vue.js", "Vuetify", "MongoDB", "Git"],
        responsibilities: [
          "Designed UI for entire client-side application to view and manage upwards of hundreds of customer contact information and emails",
          "Developed mass-emailing and file management tools to streamline client communication process",
          "Performed biweekly sprints to adjust to new stakeholder needs and additional feature implementation",
        ],
        wil: "",
        type: 0,
      },
      {
        title: "Full-Stack Web Developer & IT",
        where: "Honors College, University of South Florida, Tampa FL",
        start: new Date(2015, 8, 2),
        when: "Aug 2015 - Jan 2019",
        tools: ["C#", "ASP.NET", "JavaScript", "Bootstrap", "MsSQL"],
        responsibilities: [
          "Worked closely with college faculty to develop a scalable tech tracking and checkout system to inventory more than 100 electronic devices, all faculty workstations, and streamline professor rental of devices",
          "Streamlined tools to help advisors process more than 7,000 student records",
          "Engaged in Scrum methodologies alongside USF’s main IT developers",
        ],
        wil: "",
        type: 0,
      },
      {
        title: "Graphic Designer",
        where: "Honors College, University of South Florida, Tampa FL",
        start: new Date(2015, 8, 1),
        when: "Aug 2015 - Jan 2019",
        tools: ["Adobe Suite", "Moqups"],
        responsibilities: [
          "Designed advertisement posters for 16 study abroad programs designed to reflect each trip's destination and study themes",
          "Brainstormed and prototyped digital marquee to update the Honors College's main lobby",
          "Created new Honors College LLC logo to highlight college ideologies for merchandising and college outreach",
        ],
        wil: "",
        type: 1,
      },
      {
        title: "The Art of Experience",
        where: "Honors Thesis",
        start: new Date(2018, 1, 1),
        when: "Jan 2018 - Dec 2018",
        tools: ["Vuforia", "Unity3D", "Google Cardboard", "JavaScript"],
        responsibilities: [
          "Designed and built an art installation using VR/AR technology to combine traditional and digital art",
          "Demonstrated and presented installation to more than 50 attendees, answering questions on development, planning, and inspiration",
        ],
        wil: "",
        type: 2,
      },
      {
        title: "Art Lead",
        where: "LeapDoctor Games, LeapForward LLC",
        start: new Date(2017, 5, 1),
        when: "May 2017 - Apr 2018",
        tools: ["Unity2D", "Git", "Adobe Suite"],
        responsibilities: [
          "★ Chosen as PAX South 2017 Rising Showcaser",
          "Acted as Art Lead for small indie team, creating all assets, design, and promotional materials",
          "Mentored assistant artist in workflow, asset creation, and animation tools",
          "Presented at two game conferences to thousands of people and discussed development cycles and overall game design",
        ],
        wil: "",
        type: 1,
      },
      {
        title: "The Hole Moon",
        where: "Game Jam - Brackeys Game Jam 2020.1",
        start: new Date(2020, 2, 1),
        when: "Feb 2020",
        tools: ["Unity2D", "C#", "Git"],
        responsibilities: [
          "Placed #23 for Graphics and #157 Overall out of 723 submissions",
          "Practiced time management skills to balance regular full-time employment and submitting the completed game by the 7 day deadline",
        ],
        wil: "",
        type: 2,
      },
      {
        title: "Assistant Language Teacher",
        where: "Awaji Board of Education, Awaji, Japan",
        start: new Date(2019, 8, 1),
        when: "Aug 2019 - Aug 2020",
        tools: ["Japanese"],
        responsibilities: [
          "Demonstrated multiple times in front of 70+ education professionals on how to run a successful, smooth foreign studies class and cooperate with the Japanese home room teacher",
          "Led bilingual trainings for three schools' faculties on teaching strategies and English acquirement",
          "Overcame language barriers to effectively teach a foreign language and function as part of multiple school faculties",
        ],
        wil: "",
        type: 1,
      },
      {
        title: "Dynamic Memory",
        where: "Independent Study, University of South Florida, Tampa FL",
        start: new Date(2017, 8, 1),
        when: "Aug 2017 - Dec 2018",
        tools: ["Unity2D", "C#"],
        responsibilities: [
          "Created a canban timeline to act as a guide during the development cycle",
          "Reported bi-weekly progress updates to sponsoring professor showing completed goals, development roadblocks, next expected deliverables",
          "Produced feature-complete point-and-click adventure game within semester time-limit",
        ],
        wil: "",
        type: 2,
      },
    ],
  }),
  computed: {
    orderedResume: function() {
      let temp = this.resumeItems;
      temp.sort(function(a, b) {
        return new Date(a.start) - new Date(b.start);
      });
      return temp.reverse();
    },
  },
  methods: {
    getIcon(type) {
      switch (type) {
        case 0:
          return "mdi-code-braces-box";
        case 1:
          return "mdi-gesture";
        case 2:
          return "mdi-monitor-dashboard";
      }
    },
    getDisplay(type) {
      switch (type) {
        case 0:
          return this.showDev ? true : false;
        case 1:
          return this.showDes ? true : false;
        case 2:
          return this.showProj ? true : false;
      }
    },
  },
};
</script>
