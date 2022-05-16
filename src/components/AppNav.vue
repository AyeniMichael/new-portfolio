<template>
  <div>
    <v-app-bar app clipped-right>
      <v-app-bar-title>
        <v-btn :to="{ name: links[0].name }" text>
          <span>Ayeni M.A</span>
        </v-btn>
      </v-app-bar-title>

      <v-spacer></v-spacer>

      <v-btn
        v-for="(link, idx) in links"
        :key="idx"
        :to="{ name: link.name }"
        v-show="!mobile"
        text
      >
        {{ link.label }}
      </v-btn>

      <v-app-bar-nav-icon
        @click="drawer = !drawer"
        v-if="mobile"
      ></v-app-bar-nav-icon>
    </v-app-bar>

    <v-navigation-drawer
      app
      color="blue lighten-2"
      v-model="drawer"
      v-if="mobile"
      clipped
      right
      width="50vw"
    >
      <v-container>
        <v-row justify="center">
          <v-list nav dense class="mt-16 pt-16">
            <v-list-item v-for="(link, idx) in links" :key="idx"
              ><v-btn  :to="{ name: link.name }" text @click="drawer = false" class="black--text">
                {{ link.label }}
              </v-btn>
            </v-list-item>
          </v-list>
        </v-row>
      </v-container>
    </v-navigation-drawer>
  </div>
</template>

<script>
export default {
  name: "AppNav",
  data() {
    return {
      drawer: false,
      links: [
        {
          label: "Home",
          name: "Home",
          icon: "mdi-home",
        },
        {
          label: "About",
          name: "About",
          icon: "mdi-home",
        },
        {
          label: "Projects",
          name: "Projects",
          icon: "mdi-home",
        },

        {
          label: "Contact",
          name: "Contact",
          icon: "mdi-home",
        },
      ],
    };
  },

  computed: {
    mobile() {
      return this.$vuetify.breakpoint.smAndDown;
    },
  },

  watch: {
    mobile(newValue) {
      if (newValue) {
        this.drawer = false;
      }
    },
  },
};
</script>

<style lang="scss" scoped></style>
