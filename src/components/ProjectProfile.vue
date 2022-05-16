<template>
  <div>
    <v-sheet color="pink  py-10">
      <v-container>
        <v-card color="transparent" tile flat>
          <v-card-title class="justify-center display-1 white--text"
            >PROJECTS</v-card-title
          >
        </v-card>
      </v-container>
    </v-sheet>
    <v-sheet color="blue lighten-2" height="100%" class="py-10">
      <v-container>
        <v-row align="center">
          <v-col cols="12" md="4">
            <div data-aos="slide-up" data-aos-duration="1000">
              <v-card dark class="transparent" flat>
                <v-card-title class="headline pink--text">
                  MY WORKS</v-card-title
                >
                <v-card-subtitle class="display-1 pink--text"
                  >See some some amazing projects i've worked
                  on</v-card-subtitle
                >
                <v-card-text class="subtitle-1 black--text">
                  Hi! I’m Ayeni Michael, and I’m a developer who has passion for
                  building clean web applications with intuitive functionality.
                  I enjoy the process of turning ideas into reality using
                  creative solutions
                </v-card-text>
              </v-card>
            </div>
          </v-col>
          <v-col
            cols="12"
            md="4"
            sm="6"
            v-for="(work, idx) in works"
            :key="idx"
          >
            <div
              data-aos="slide-up"
              data-aos-duration="1000"
              data-aos-delay="100"
            >
              <v-card height="250" class="pt-10 text-center">
                <v-card-title class="justify-center">{{
                  work.title
                }}</v-card-title>
                <v-card-text>{{ work.description }}</v-card-text>
              </v-card>
            </div>
          </v-col>
        </v-row>
        <div
          class="text-center"
          data-aos="slide-up"
          data-aos-duration="1000"
          data-aos-delay="100"
        >
          <v-btn width="200" height="50" class="mt-4">SEE MORE</v-btn>
        </div>
      </v-container>
    </v-sheet>
  </div>
</template>

<script>
export default {
  data() {
    return {
      works: [
        {
          title: "Coming soon...",
          description: "A complete web app solution for business",
          icon: "mdi-database-settings",
        },
        {
          title: "Coming soon...",
          description: "A complete web app solution for business",
          icon: "mdi-database-settings",
        },
        {
          title: "Coming soon...",
          description: "A complete web app solution for business",
          icon: "mdi-database-settings",
        },
        {
          title: "Coming soon...",
          description: "A complete web app solution for business",
          icon: "mdi-database-settings",
        },
        {
          title: "Coming soon...",
          description: "A complete web app solution for business",
          icon: "mdi-database-settings",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped></style>
