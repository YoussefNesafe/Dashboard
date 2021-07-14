<template>
  <v-footer dark padless app inset>
    <v-card class="flex" flat tile color="blue accent-3" :elevation="10">
      <v-card-text class="py-2 white--text text-center">
        {{ new Date().getFullYear() }}/{{ new Date().getMonth() }}/{{
          new Date().getDay()
        }}
        - <strong>YN</strong>
      </v-card-text>
    </v-card>
  </v-footer>
</template>
