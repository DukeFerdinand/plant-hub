<template>
  <v-app dark="false">
    <v-navigation-drawer v-model="navHidden" color="success" fixed app>
      <v-list>
        <v-list-item v-for="item in items" :key="item.to" :to="item.to">
          {{ item.title }}
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar elevation="0" color="white" :clipped-left="clipped" fixed app>
      <v-app-bar-nav-icon @click.stop="navHidden = !navHidden" />
      <v-toolbar-title>The IoT Hub</v-toolbar-title>
    </v-app-bar>
    <v-main>
      <v-container class="p-0">
        <nuxt />
      </v-container>
    </v-main>
  </v-app>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  data() {
    return {
      // TODO: Add routes here
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/',
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Inspire',
          to: '/inspire',
        },
      ],
      navHidden: false,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js',
    }
  },
})
</script>
