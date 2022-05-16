<template>
  <div>
    <v-sheet color="pink  py-10">
      <v-container>
        <v-card color="transparent" tile flat>
          <v-card-title class="justify-center display-1 white--text"
            >ABOUT ME</v-card-title
          >
        </v-card>
      </v-container>
    </v-sheet>
    <v-sheet class="blue lighten-2" height="70%">
      <v-container fill-height>
        <v-row align="center">
          <v-col cols="12" md="5">
            <div data-aos="slide-up" data-aos-duration="500">
              <v-card class="transparent" dark flat>
                <v-card-title class="title pink--text lighten-2"
                  >HEY! I AM</v-card-title
                >
                <v-card-subtitle class="display-2 black--text"
                  >Michael Ayeni</v-card-subtitle
                >
                <v-card-text class="headline pink--text"
                  >I'm a Developer</v-card-text
                >
                <v-card-text class="subtitle-1 black--text"
                  >Hi! I’m Ayeni Michael, and I’m a developer who has passion
                  for building clean web applications with intuitive
                  functionality. I enjoy the process of turning ideas into
                  reality using creative solutions</v-card-text
                >
              </v-card>
            </div>
          </v-col>
          <v-col cols="12" md="7" v-if="!mobile">
            <div
              data-aos="slide-up"
              data-aos-duration="500"
              data-aos-easing="ease-in"
            >
              <v-card class="transparent" flat tile>
                <v-img
                  :src="`img/avatar.png`"
                  max-height="450"
                  max-width="350"
                  class="mx-auto"
                >
                </v-img>
              </v-card>
            </div>
          </v-col>
        </v-row>
      </v-container>
    </v-sheet>
    <v-sheet color="pink">
      <v-container>
        <v-card color="transparent" tile flat>
          <v-card-title class="justify-center headline white--text"
            >MY RESUME</v-card-title
          >
        </v-card>
      </v-container>
    </v-sheet>
    <v-sheet class="blue lighten-2" height="100%">
      <v-container fill-height class="py-10">
        <v-row align="center">
          <v-col cols="12" md="6">
            <div data-aos="slide-up" data-aos-duration="700">
              <v-card>
                <div class="pt-5 text-center headline">Education</div>
                <v-timeline dense>
                  <v-timeline-item
                    right
                    v-for="(edu, i) in education"
                    :key="i"
                    :color="edu.color"
                    small
                  >
                    <v-row>
                      <v-col cols="12" sm="3">
                        <v-card-title class="body-2 pb-0">
                          {{ edu.startDate }} - <br />
                          {{ edu.endDate }}
                        </v-card-title>
                      </v-col>
                      <v-col cols="12" sm="9">
                        <v-card-subtitle class="pt-0">
                          <strong>{{ edu.course }}</strong
                          ><br />
                          {{ edu.school }}
                        </v-card-subtitle>
                        <v-card-text> </v-card-text>
                      </v-col>
                    </v-row>
                  </v-timeline-item>
                </v-timeline>
              </v-card>
            </div>
          </v-col>
          <v-col cols="12" md="6">
            <div
              data-aos="slide-up"
              data-aos-duration="700"
              data-aos-easing="ease-in"
            >
              <v-card>
                <div class="pt-5 text-center headline">Experience</div>
                <v-timeline dense>
                  <v-timeline-item
                    right
                    v-for="(exp, i) in experience"
                    :key="i"
                    :color="exp.color"
                    small
                  >
                    <v-row>
                      <v-col cols="12" sm="3">
                        <v-card-title class="body-2 pb-0">
                          {{ exp.startDate }} - <br />
                          {{ exp.endDate }}
                        </v-card-title>
                      </v-col>
                      <v-col cols="12" sm="9">
                        <v-card-subtitle class="pt-0">
                          <strong>{{ exp.jobRole }}</strong
                          ><br />
                          {{ exp.organization }}
                        </v-card-subtitle>
                      </v-col>
                    </v-row>
                  </v-timeline-item>
                </v-timeline>
              </v-card>
            </div>
          </v-col>
        </v-row>
      </v-container>
    </v-sheet>
    <v-sheet color="pink">
      <v-container>
        <v-card color="transparent" tile flat>
          <v-card-title class="justify-center headline white--text"
            >SKILL COMPETENCY</v-card-title
          >
        </v-card>
      </v-container>
    </v-sheet>
    <v-sheet class="blue lighten-2" height="100%">
      <v-container fill-height class="py-10">
        <v-row align="center">
          <v-col cols="12" md="6">
            <div data-aos="slide-up" data-aos-duration="700">
              <v-card
                v-for="(skill, i) in frontEndSkills"
                :key="i"
                class="mt-5 transparent"
              >
                <v-card-title class="black--text">
                  {{ skill.name }}</v-card-title
                >
                <v-progress-linear
                  :value="skill.value"
                  color="pink"
                  height="25"
                  class="white--text"
                  >{{ skill.value }}%</v-progress-linear
                >
              </v-card>
            </div>
          </v-col>
          <v-col cols="12" md="6">
            <div
              data-aos="slide-up"
              data-aos-duration="700"
              data-aos-easing="ease-in"
            >
              <v-card
                v-for="(skill, i) in backEndSkills"
                :key="i"
                class="mt-5 transparent"
              >
                <v-card-title class="black--text">
                  {{ skill.name }}</v-card-title
                >
                <v-progress-linear
                  :value="skill.value"
                  color="pink"
                  height="25"
                  class="white--text"
                  >{{ skill.value }}%</v-progress-linear
                >
              </v-card>
            </div>
          </v-col>
        </v-row>
      </v-container>
    </v-sheet>
  </div>
</template>

<script>
export default {
  name: "AboutProfile",
  data() {
    return {
      frontEndSkills: [
        {
          name: "Vue.js",
          value: 76,
        },
        {
          name: "HTML & CSS",
          value: 85,
        },
        {
          name: "Javascript",
          value: 80,
        },
      ],
      backEndSkills: [
        {
          name: "php",
          value: 80,
        },
        {
          name: "Laravel",
          value: 85,
        },
        {
          name: "MYSql",
          value: 75,
        },
      ],
      experience: [
        {
          startDate: "JUL 2016",
          endDate: "DEC 2016",
          jobRole: "Software Intern",
          organization:
            "Bureau of Information and Communication Technology, Ado, Ekiti",
          color: "blue",
        },
        {
          startDate: "OCT 2017",
          endDate: "OCT 2018",
          jobRole: "Software Developer",
          organization: "Federal University of Technology, CRC, Akure",
          color: "pink",
        },
        {
          startDate: "OCT 2021",
          endDate: "Present",
          jobRole: "Front End Developer",
          organization: "Kinplus Technologies",
          color: "blue",
        },
      ],

      education: [
        {
          startDate: "OCT 2013",
          endDate: "JUL 2017",
          course: "B.Sc Computer Science",
          school: "Joseph Ayo Babalola University",
          color: "pink",
        },
        {
          startDate: "FEB 2020",
          endDate: "Present",
          course: "Full Stack web development",
          school: "Kinplus Technologies",
          color: "blue",
        },
        {
          startDate: "MAR 2019",
          endDate: "Present",
          course: "M.Tech Computer Science",
          school: "Federal University of Technology",
          color: "pink",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped></style>
