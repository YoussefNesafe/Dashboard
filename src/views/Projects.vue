<template>
  <div class="projects">
    <h1 class="subheading grey--text">Project</h1>
    <v-container>
      <v-layout row wrap class="mb-4">
        <v-tooltip bottom>
          <template v-slot:activator="{ on }">
            <v-btn
              small
              outlined
              color="green"
              @click="sortBy('title')"
              class="mr-2"
              dark
              v-on="on"
            >
              <v-icon left small>folder</v-icon>
              <span class="caption text-lowercase">By project Title</span>
            </v-btn>
          </template>
          <span>Sort Project</span>
        </v-tooltip>
        <v-tooltip bottom>
          <template v-slot:activator="{ on }">
            <v-btn
              small
              outlined
              color="green"
              @click="sortBy('person')"
              class="mr-2"
              dark
              v-on="on"
            >
              <v-icon left small>person</v-icon>
              <span class="caption text-lowercase">By Name</span>
            </v-btn>
          </template>
          <span>Sort Name</span>
        </v-tooltip>
        <v-tooltip bottom>
          <template v-slot:activator="{ on }">
            <v-btn
              small
              outlined
              color="green"
              @click="sortBy('due')"
              class="mr-2"
              dark
              v-on="on"
            >
              <v-icon left small>date</v-icon>
              <span class="caption text-lowercase">By Date</span>
            </v-btn>
          </template>
          <span>Sort Date</span>
        </v-tooltip>
      </v-layout>
      <v-card
        flat
        v-for="project in projects"
        :key="project.title"
        class="mb-4"
      >
        <v-layout row wrap :class="`pa-3 project ${project.status}`">
          <v-flex xs12 md6>
            <div class="caption grey--text">Name</div>
            <div>{{ project.person }}</div>
          </v-flex>
          <v-flex xs6 sm4 md2>
            <div class="caption grey--text">Due By</div>
            <div>{{ project.due }}</div>
          </v-flex>
        </v-layout>
      </v-card>
    </v-container>
  </div>
</template>
<script>
export default {
  data: () => ({
    projects: [
      {
        title: "Site Web",
        person: "youssef",
        due: "10/10/2010",
        status: "complete",
      },
      {
        title: "Application Mobile Web",
        person: "Mohamad",
        due: "20/10/2011",
        status: "complete",
      },
      {
        title: "Conception",
        person: "Ali",
        due: "10/12/2012",
        status: "yes",
      },
      { title: "AI", person: "Ahmad", due: "10/12/2020", status: "up" },
    ],
  }),
  methods: {
    sortBy(prop) {
      this.projects.sort((a, b) => (a[prop] < b[prop] ? -1 : 1));
    },
  },
};
</script>
<style>
.project.complete {
  background: rgba(60, 209, 194, 0.5);
}
.project.no {
  background: rgba(255, 165, 0, 0.5);
}
.project.up {
  background: rgba(255, 0, 0, 0.5);
}
.project.yes {
  background: rgba(255, 255, 0, 0.5);
}
</style>
