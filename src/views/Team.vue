<template>
  <div>
    <h1 class="subheading grey--text">Our Team</h1>
    <v-container>
      <v-layout row wrap>
        <v-flex xs12 sm6 md4 lg3 v-for="person in team" :key="person.name">
          <v-card class="text-center ma-3">
            <v-responsive class="pt-4">
              <v-avatar size="100" class="blue accent-3">
                <v-img :src="person.avatar"></v-img>
              </v-avatar>
            </v-responsive>
            <v-card-text>
              <div class="subheading">{{ person.name }}</div>
              <div class="grey--text">{{ person.role }}</div>
            </v-card-text>
            <v-card-actions>
              <v-btn outlined color="blue accent-3">
                <v-icon small left>message</v-icon>
                <span>Message</span>
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-flex>
      </v-layout>
    </v-container>
  </div>
</template>

<script>
export default {
  data: () => ({
    team: [
      {
        name: "youssef",
        role: "Web Developer",
        avatar: "/user.jpg",
      },
      {
        name: "Ali",
        role: "Web Developer",
        avatar: "/user.jpg",
      },
      {
        name: "Mohammad",
        role: "graphic designer",
        avatar: "/user.jpg",
      },
    ],
  }),
};
</script>
