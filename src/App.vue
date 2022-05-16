<template>
  <v-app>
    <app-nav></app-nav>
    <v-main>
      <router-view />
    </v-main>
    <Footer />
  </v-app>
</template>

<script>
import AppNav from "@/components/AppNav.vue";
import Footer from "./components/Footer.vue";
export default {
  name: "App",
  components: { AppNav, Footer },
  data: () => ({
    //
  }),
};
</script>
