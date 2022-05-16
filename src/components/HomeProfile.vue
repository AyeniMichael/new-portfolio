<template>
  <div>
    <v-sheet class="blue lighten-2" height="90vh">
      <v-container fill-height>
        <v-row align="center">
          <v-col cols="12" md="5">
            <div data-aos="slide-up" data-aos-duration="1000">
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

              <v-btn class="ml-4 rounded-pill"> DOWNLOAD CV </v-btn>
            </div>
          </v-col>
          <v-col cols="12" md="7" v-if="!mobile">
            <div
              data-aos="slide-up"
              data-aos-duration="1000"
              data-aos-easing="ease-in"
            >
              <v-card class="transparent" flat tile>
                <v-img
                  :src="`img/avatar.png`"
                  max-height="500"
                  max-width="400"
                  class="mx-auto"
                >
                </v-img>
              </v-card>
            </div>
          </v-col>
        </v-row>
      </v-container>
    </v-sheet>

    <v-sheet color="pink" height="100%" class="py-10">
      <v-container fill-height>
        <v-row align="center">
          <v-col cols="12" md="6">
            <div data-aos="slide-up" data-aos-duration="700">
              <v-card class="transparent" dark flat>
                <v-card-title class="headline">MY SERVICES</v-card-title>
                <v-card-subtitle class="display-2"
                  >How can i help?</v-card-subtitle
                >
                <v-card-text class="subtitle-1">
                  I provide services including Frontend Design, Backend Design,
                  Full Stack web applications, Wordpress Website
                  Design</v-card-text
                >
              </v-card>
            </div>
          </v-col>
          <v-col cols="12" md="6">
            <v-row>
              <v-col
                cols="12"
                md="6"
                sm="6"
                v-for="(service, idx) in services"
                :key="idx"
              >
                <div
                  data-aos="slide-up"
                  data-aos-duration="700"
                  data-aos-delay="100"
                >
                  <v-card height="250" class="pt-10 text-center">
                    <v-card
                      flat
                      color="grey lighten-2"
                      width="40"
                      height="40"
                      class="mx-auto"
                    >
                      <v-icon class="pt-2"> {{ service.icon }} </v-icon>
                    </v-card>
                    <v-card-title class="justify-center">{{
                      service.title
                    }}</v-card-title>
                    <v-card-text>{{ service.description }}</v-card-text>
                  </v-card>
                </div>
              </v-col>
            </v-row>
          </v-col>
        </v-row>
      </v-container>
    </v-sheet>
    <v-sheet color="blue lighten-2" height="100%" class="py-10">
      <v-container>
        <v-row>
          <v-col cols="12" md="6">
            <div
              data-aos="slide-up"
              data-aos-duration="700"
              data-aos-delay="100"
            >
              <v-card class="transparent white--text" flat>
                <v-card-title class="headline pink--text">
                  MY SKILLS</v-card-title
                >
                <v-card-subtitle class="display-1 pink--text"
                  >Here are Languages and Tools i utilize</v-card-subtitle
                >
                <v-card-text class="subtitle-1 black--text">
                  I develop simple, intuitive, responsive and intelligent web
                  application solutions that helps users get things done with
                  less effort and time with these stack of tools.
                </v-card-text>
              </v-card>
            </div></v-col
          >

          <v-col cols="12" md="6">
            <v-card>
              <v-tabs
                v-model="tab"
                background-color="pink accent-4"
                centered
                dark
                icons-and-text
              >
                <v-tabs-slider></v-tabs-slider>

                <v-tab>
                  Skills
                  <v-icon>mdi-phone</v-icon>
                </v-tab>

                <v-tab>
                  Tools
                  <v-icon>mdi-heart</v-icon>
                </v-tab>
              </v-tabs>
            </v-card>
            <v-card class="transparent pa-5">
              <v-tabs-items v-model="tab" class="transparent">
                <v-tab-item>
                  <v-container fluid>
                    <v-row class="justify-center">
                      <v-col
                        md="3"
                        sm="2"
                        v-for="(skill, idx) in skills"
                        :key="idx"
                      >
                        <v-tooltip top>
                          <template v-slot:activator="{ on, attrs }">
                            <v-btn
                              icon
                              color="pink"
                              v-bind="attrs"
                              v-on="on"
                              class="white pa-8"
                            >
                              <v-icon x-large>{{ skill.icon }}</v-icon>
                            </v-btn>
                          </template>
                          <span>{{ skill.title }}</span>
                        </v-tooltip>
                      </v-col>
                    </v-row>
                  </v-container>
                </v-tab-item>
                <v-tab-item>
                  <v-container fluid>
                    <v-row class="justify-center">
                      <v-col
                        md="3"
                        sm="2"
                        v-for="(tool, idx) in tools"
                        :key="idx"
                      >
                        <v-tooltip top>
                          <template v-slot:activator="{ on, attrs }">
                            <v-btn
                              icon
                              color="pink"
                              v-bind="attrs"
                              v-on="on"
                              class="white pa-8"
                            >
                              <v-icon x-large>{{ tool.icon }}</v-icon>
                            </v-btn>
                          </template>
                          <span>{{ tool.title }}</span>
                        </v-tooltip>
                      </v-col>
                    </v-row>
                  </v-container>
                </v-tab-item>
              </v-tabs-items>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-sheet>
    <v-sheet color="pink" height="100%" class="py-10">
      <v-container>
        <v-row align="center">
          <v-col cols="12" md="4">
            <div data-aos="slide-up" data-aos-duration="1000">
              <v-card dark class="transparent" flat>
                <v-card-title class="headline"> MY WORKS</v-card-title>
                <v-card-subtitle class="display-1"
                  >See some some amazing projects i've worked
                  on</v-card-subtitle
                >
                <v-card-text class="subtitle-1">
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
              data-aos-duration="900"
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
          data-aos-duration="500"
          data-aos-delay="100"
        >
          <v-btn width="200" height="50" class="mt-4">SEE MORE</v-btn>
        </div>
      </v-container>
    </v-sheet>
    <v-sheet color="blue lighten-2" height="100%" class="py-10">
      <v-container>
        <v-row justify="center">
          <v-col cols="12" md="6">
            <div
              data-aos="slide-up"
              data-aos-duration="900"
              data-aos-delay="100"
            >
              <v-card dark class="transparent" flat>
                <v-card-title class="headline pink--text">
                  LATEST BLOG POST</v-card-title
                >
                <v-card-subtitle class="display-1 pink--text"
                  >See some some amazing articles i've worked
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
          <v-col cols="12" md="6">
            <div
              data-aos="slide-up"
              data-aos-duration="800"
              data-aos-delay="100"
            >
              <v-carousel
                cycle
                height="250"
                hide-delimiter-background
                hide-delimiters
                :show-arrows="false"
                interval="4000"
              >
                <v-carousel-item
                  v-for="(item, idx) in blogItems"
                  :key="idx"
                  :src="`img/${item.image}`"
                >
                </v-carousel-item>
              </v-carousel>

              <v-card width="80%" class="mx-auto mt-n16 rounded-0">
                <v-card-subtitle>
                  <v-icon color="pink">mdi-calendar-month-outline</v-icon>
                  12 July 2016 | <v-icon color="pink">mdi-heart</v-icon> 245 |
                  <v-icon color="pink">mdi-comment</v-icon> 24
                </v-card-subtitle>
                <v-card-title>Coming Soon...</v-card-title>
                <v-card-text class="subtitle-1">
                  Hi! I’m Ayeni Michael, and I’m a developer who has passion for
                  building clean web applications with intuitive functionality.
                  I enjoy the process of turning ideas into reality using
                  creative solutions Hi! I’m Ayeni Michael, and I’m a developer
                  who has passion for building clean web applications with
                  intuitive functionality.
                </v-card-text>
              </v-card>
            </div>
          </v-col>
          <v-container>
            <v-row>
              <v-col
                cols="12"
                md="6"
                sm="6"
                v-for="(item, idx) in blogItems"
                :key="idx"
              >
                <div
                  data-aos="slide-up"
                  data-aos-duration="900"
                  data-aos-delay="100"
                >
                  <v-card>
                    <v-img
                      aspect-ratio="1"
                      :src="`img/${item.image}`"
                      height="200"
                      class="mb-5"
                    >
                    </v-img>
                    <v-card-subtitle>
                      <v-icon color="pink">mdi-calendar-month-outline</v-icon>
                      12 July 2016 | <v-icon color="pink">mdi-heart</v-icon> 245
                      | <v-icon color="pink">mdi-comment</v-icon> 24
                    </v-card-subtitle>
                    <v-card-title>Coming Soon...</v-card-title>
                    <v-card-text class="subtitle-1">{{
                      item.description
                    }}</v-card-text>
                  </v-card>
                </div>
              </v-col>
            </v-row>
          </v-container>
        </v-row>
      </v-container>
    </v-sheet>
    <v-sheet color="pink" height="100%" class="py-10">
      <v-container fill-height>
        <v-row>
          <v-col cols="12" md="6">
            <v-card class="transparent" flat>
              <v-card-title class="headline white--text"
                >TESTIMONIALS</v-card-title
              >
              <v-card-subtitle
                class="d-flex justify-center display-1 white--text"
                >Check out what my clients say about me</v-card-subtitle
              >
              <v-card-text class="subtitle-1 white--text"
                >I've offered services to individuals and organizations and they
                have wonderful things to say about me
              </v-card-text>
            </v-card>
          </v-col>
          <v-col cols="12" md="6">
            <v-carousel
              cycle
              height="250"
              width="400"
              class="d-flex justify-center"
              hide-delimiter-background
              hide-delimiters
              show-arrows-on-hover
              interval="4000"
            >
              <v-carousel-item
                v-for="(testimony, idx) in testimonials"
                :key="idx"
              >
                <v-card color="blue lighten-2">
                  <v-card-text class="text-center subtitle-1">
                    {{ testimony.testimony }}
                  </v-card-text>
                  <v-card-title class="justify-center">{{
                    testimony.name
                  }}</v-card-title>
                  <v-card-subtitle class="text-center pb-5">{{
                    testimony.occupation
                  }}</v-card-subtitle>
                </v-card>
              </v-carousel-item>
            </v-carousel>
          </v-col>
        </v-row>
      </v-container>
    </v-sheet>
  </div>
</template>

<script>
export default {
  name: "HomeProfile",
  computed: {
    mobile() {
      return this.$vuetify.breakpoint.smAndDown;
    },
  },
  data() {
    return {
      skilltoggle: false,
      text: "Test",
      tab: null,
      services: [
        {
          title: "Frontend Design",
          description: "Bring designs and wireframes to live",
          icon: "mdi-database-settings",
        },
        {
          title: "Backend Design",
          description: "Construct intelligent and efficient web applications",
          icon: "mdi-database-settings",
        },
        {
          title: "Wordpress Website",
          description: "Create effective wordpress sites for your business",
          icon: "mdi-database-settings",
        },
        {
          title: "Database Management",
          description:
            "Acquire, store and offer a variety of data presentation",
          icon: "mdi-database-settings",
        },
      ],
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
      tabTitle: ["Skills", "Tools"],
      skills: [
        {
          title: "HTML5",
          icon: "mdi-language-html5",
        },
        {
          title: "CSS3",
          icon: "mdi-language-css3",
        },
        {
          title: "BOOTSTRAP",
          icon: "mdi-bootstrap",
        },
        {
          title: "jQUERY",
          icon: "mdi-jquery",
        },
        {
          title: "JAVASCRIPT",
          icon: "mdi-language-javascript",
        },
        {
          title: "TYPESCRIPT",
          icon: "mdi-language-typescript",
        },
        {
          title: "PHP",
          icon: "mdi-language-php",
        },
        {
          title: "LARAVEL",
          icon: "mdi-laravel",
        },
        {
          title: "VUE",
          icon: "mdi-vuejs",
        },
        {
          title: "TAILWIND CSS",
          icon: "mdi-tailwind",
        },
        {
          title: "VUETIFY",
          icon: "mdi-vuetify",
        },

        {
          title: "SQL",
          icon: "mdi-database",
        },
        {
          title: "FIREBASE",
          icon: "mdi-firebase",
        },
      ],
      tools: [
        {
          title: "VSCODE",
          icon: "mdi-microsoft-visual-studio-code",
        },
        {
          title: "Webpack",
          icon: "mdi-webpack",
        },
        {
          title: "git",
          icon: "mdi-git",
        },
        {
          title: "github",
          icon: "mdi-github",
        },
        {
          title: "npm",
          icon: "mdi-npm",
        },
        {
          title: "slack",
          icon: "mdi-slack",
        },
      ],
      blogItems: [
        {
          image: "3.jpg",
          description:
            "Hi! I’m Ayeni Michael, and I’m a developer who has passion for building clean web applications with intuitive functionality. I enjoy the process of turning ideas into reality using creative solutions",
        },
        {
          image: "4.jpg",
          description:
            "Hi! I’m Ayeni Michael, and I’m a developer who has passion for building clean web applications with intuitive functionality. I enjoy the process of turning ideas into reality using creative solutions",
        },
      ],
      testimonials: [
        {
          testimony:
            "cursus quis hendrerit ac, elementum non orci. Praesent iaculis est eu dictum imperdiet.",
          name: "Michael Ayeni",
          occupation: "Programmer",
        },
        {
          testimony:
            "cursus quis hendrerit ac, elementum non orci. Praesent iaculis est eu dictum imperdiet. Sed eget erat vitae est tincidunt finibus.",
          name: "John Ayeni",
          occupation: "Programmer",
        },
        {
          testimony:
            "cursus quis hendrerit ac, elementum non orci. Praesent iaculis est eu dictum imperdiet. Sed eget erat vitae est tincidunt finibus.",
          name: "Michael Savus",
          occupation: "Programmer",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped></style>
