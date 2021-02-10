<template>
  <v-container fluid>
    <v-row justify="center" class="text-center text-h3  font-weight-bold mb-5">
      <v-col> <span class="gradienttext">My Resume</span></v-col>
    </v-row>

    <v-row class="white--text mb-5">
      <v-col
        cols="12" md="3" lg="2"
        class="border-rightb font-weight-medium text-right text-h5 mr-5 pr-5"
      >
        Education
      </v-col>
      <v-col class="pb-0">
        <v-row class="font-weight-medium">
          <v-col class="py-0 text-h5"> Bachelor's in Computer Science</v-col>
        </v-row>
        <v-row class="text-h6 blue--text">
          <v-col cols="12" md="6" class="py-0">University of South Florida</v-col>
          <v-col class="py-0">Aug 2013 - Dec 2018</v-col>
        </v-row>
        <v-row>
          <v-col
            ><p>
              Graduated from Engineering with a GPA of 3.5, as well as completed
              Honors College curriculum and thesis. Here I studied the
              foundation of programming, including data structures,
              object-oriented-programming, and algorithms. I specialized in
              automata theory and introductory AI, as well as completed
              independent research.
            </p></v-col
          >
        </v-row>
      </v-col>
    </v-row>
    <v-row><v-col></v-col></v-row>
    <v-row class="white--text mt-5">
      <v-col
        cols="12" md="3" lg="2"
        class="border-rightp font-weight-medium text-right text-h5 mr-5 pr-5"
      >
        Experience
      </v-col>
      <v-col class="py-0">
        <v-row v-for="(item, i) in orderedResume" :key="i">
          <v-col>
            <v-row>
              <v-col class=" text-h5 py-0" cols="12">{{ item.title }}</v-col>
              <v-col cols="12" class="deep-orange--text text--lighten-3 pt-0"
                >{{ item.where }} ~ {{ item.when }}</v-col
              >
            </v-row>
            <v-row>
              <v-col
                class="pt-0"
                v-for="(tool, t) in item.tools"
                :key="t"
                sm="2"
                ><span class="amber--text text--lighten-4">{{
                  tool
                }}</span></v-col
              >
              <v-spacer></v-spacer>
            </v-row>
            <v-row>
              <v-col class="pt-0 pb-5">
                <ul>
                  <li v-for="(rsp, r) in item.responsibilities" :key="r">
                    {{ rsp }}
                  </li>
                </ul>
              </v-col>
            </v-row>
          </v-col>

          
        </v-row>
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
        tools: ["JavaScript", "Vue.js", "Vuetify", "MongoDB", "Git", "Agile"],
        responsibilities: [
          "Assumed the UI designer role to fill gap in team needs",
          "Redesigned 7 client-side views to manage hundreds of customer contact information and emails",
          "Prepared detailed mockups to assist teammates with desktop and mobile responsive styling",
          "Implemented mass-emailing and file management tools according to client feedback",
          "Produced new graphic designs for rebranding of platform and company",
          "Performed biweekly sprints to address stakeholder needs and additional features",
        ],
        color: "#1E88E5",
        type: 0,
      },
      {
        title: "Student Web Developer & IT",
        where: "Honors College, University of South Florida, Tampa FL",
        start: new Date(2015, 8, 2),
        when: "Aug 2015 - Jan 2019",
        tools: ["C#", "ASP.NET", "JavaScript", "Bootstrap", "MSSQL"],
        responsibilities: [
          "Coordinated with college faculty to develop 3 new forms for student processing",
          "Proposed and prototyped a scalable tech tracking system to manage more than 100 electronic devices and 30 faculty workstations",
          "Reduced average advising session times by 15% by streamlining tools for one-on-one student advising and check-in systems",
          "Improved workflow for advisors by assimilating 4 smaller tools into 1 dashboard",
          "Managed SQL database containing more than 7,000 student records",
          "Introduced Bootstrap to student dev team to enhance structure and accessibility of website",
          "Engaged in Scrum methodologies alongside USF’s main IT developers"
        ],
        color: "#1E88E5",
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
        color: " #fe4866",
        type: 1,
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
        color: " #fe4866",
        type: 1,
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
        color: "#FFB74D",
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
          return "mdi-star";
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

<style scoped>


.border-rightb {
  border-right: 1px solid #3addea;
}

.border-rightp {
  border-right: 1px solid #ff6666;
}
</style>
