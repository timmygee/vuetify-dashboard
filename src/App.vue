<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <v-toolbar-title>
        Vuetify Dashboard
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
        v-for="link in links"
        :key="`${link.label}-header-link`"
        :to="link.url"
        text
        rounded
      >
        {{ link.label }}
      </v-btn>
    </v-app-bar>
    <v-content>
      <router-view></router-view>
    </v-content>
    <v-footer color="primary lighten-1" padless>
      <v-row justify="center" no-gutters>
        <v-btn
          v-for="link in links"
          :key="`${link.label}-footer-link`"
          :to="link.url"
          color="white"
          text
          rounded
          class="my-2"
        >
          {{ link.label }}
        </v-btn>
        <v-col class="primary lighten-2 py-4 text-center white--text" cols="12">
          {{ new Date().getFullYear() }} — <strong>Vuetify Dashboard</strong>
        </v-col>
      </v-row>
    </v-footer>
  </v-app>
</template>

<script>
// import HelloWorld from "./components/HelloWorld";

export default {
  name: 'App',

  components: {
    // HelloWorld
  },

  data: () => ({
    showPassword: false,
    links: [
      {
        url: '/',
        label: 'Home',
      },
      {
        url: '/login',
        label: 'Login',
      },
      {
        url: '/dashboard',
        label: 'Dashboard',
      },
    ],
  }),
};
</script>
