<template>
  <div>
    <!-- Start Navbar  -->
    <v-app-bar color="blue accent-3" app dark>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title>YN</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-menu offset-y>
        <template v-slot:activator="{ on }">
          <v-btn text v-on="on" class="mr-3">
            <v-icon left>expand_more</v-icon>
            <span>Menu</span>
          </v-btn>
        </template>
        <v-list flat>
          <v-list-item
            v-for="link in links"
            :key="link.text"
            router
            :to="link.route"
            active-class="border"
          >
            <v-list-item-title text-uppercase>{{
              link.text
            }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
      <v-btn text>
        <span>Exit</span>
        <v-icon right>exit_to_app</v-icon>
      </v-btn>
    </v-app-bar>
    <!-- End Navbar  -->

    <!-- Start Sidebar  -->
    <v-navigation-drawer v-model="drawer" color="blue accent-3" dark app>
      <v-layout column align-center>
        <v-flex class="mt-5">
          <v-avatar size="100">
            <v-img src="../../../public/user.jpg" alt="John"></v-img>
          </v-avatar>
          <p class="white--text subheading mt-1 text-center">Username</p>
        </v-flex>
        <v-flex class="mt-4 mb-4">
          <Popup />
        </v-flex>
      </v-layout>
      <v-list flat>
        <v-list-item
          v-for="link in links"
          :key="link.text"
          router
          :to="link.route"
          active-class="border"
        >
          <v-list-item-acion>
            <v-icon class="mr-2">{{ link.icon }}</v-icon>
          </v-list-item-acion>
          <v-list-item-content>
            <v-list-item-title>{{ link.text }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <!-- End Sidebar  -->
  </div>
</template>
<script>
  import Popup from "./Popup.vue";
  export default {
    data: () => ({
      drawer: true,
      links: [
        { icon: "dashboard", text: "Dashboard", route: "/" },
        { icon: "folder", text: "My Project", route: "/projects" },
        { icon: "person", text: "Team", route: "/team" },
      ],
    }),
    components: {
      Popup,
    },
  };
</script>
<style lang="scss" scoped>
  .border {
    border-left: 4px solid #00ff00;
  }
</style>
