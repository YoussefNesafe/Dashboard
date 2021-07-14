<template>
  <v-app>
    <Navbar />
    <v-content class="ma-4">
      <router-view></router-view>
    </v-content>
    <Footer />
  </v-app>
</template>
<script>
import Navbar from "@/components/global/Navbar.vue";
import Footer from "@/components/global/Footer.vue";
export default {
  name: "App",
  components: {
    Navbar,
    Footer,
  },
};
</script>
