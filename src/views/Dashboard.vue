<template>
  <div>
    <h1 class="subheading grey--text">Dashboard</h1>
    <v-container>
      <v-layout row wrap>
        <v-flex sm6 xs12 md6 lg3 v-for="info in infos" :key="info.id">
          <v-card class="ma-3">
            <v-list-item>
              <v-list-item-avatar tile class="mt-n7">
                <v-sheet color="green" width="40" height="40" elevation="10">
                  <v-icon dark large> {{ info.icon }}</v-icon>
                </v-sheet>
              </v-list-item-avatar>
              <v-list-item-content>
                <div class="overline text-right">{{ info.title }}</div>
                <v-list-item-title class="headline mb-1 text-right">
                  {{ info.id }}
                </v-list-item-title>
                <div><v-divider></v-divider></div>
              </v-list-item-content>
            </v-list-item>
            <v-card-actions>
              <v-icon text class="ma-2">person</v-icon>
              <div class="overline">{{ info.name }}</div>
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
      infos: [
        { icon: "store", title: "Artical", id: 523615, name: "Youssef" },
        { icon: "store", title: "Blog", id: 523616, name: "Ali" },
        { icon: "store", title: "Essae", id: 523617, name: "Mohamad" },
        { icon: "store", title: "Artical", id: 523618, name: "Lana" },
        { icon: "store", title: "Artical", id: 523619, name: "Aya" },
      ],
    }),
  };
</script>
