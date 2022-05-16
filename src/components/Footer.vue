<template>
  <div>
    <v-footer color="pink accent-4" dense padless>
      <v-row justify="center" no-gutters>
        <v-btn
          v-for="item in footerIcons"
          :key="item.id"
          color="white"
          text
          rounded
          class="my-2"
          :href="item.link"
          target="blank"
        >
          <v-icon> {{ item.icon }} </v-icon>
        </v-btn>
        <v-col
          class="py-4 text-center white--text"
          color="rgba(255,0,0,0.6)"
          dense
          dark
          cols="12"
        >
          {{ new Date().getFullYear() }} — <strong>Ayeni Michael</strong>
        </v-col>
      </v-row>
    </v-footer>
  </div>
</template>

<script>
export default {
  name: "Footer",
  data: () => ({
    footerIcons: [
      {
        icon: "mdi-linkedin",
        link: "https://www.linkedin.com/in/ayeni-michael-1913a3167/",
      },
      {
        icon: "mdi-github",
        link: "https://github.com/AyeniMichael",
      },
      {
        icon: "mdi-codepen",
        link: "https://codepen.io/AyeniMichael",
      },
    ],
  }),
};
</script>
