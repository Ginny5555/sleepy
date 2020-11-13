<template>
  <v-app id="app">
    <router-view />
  </v-app>
</template>
<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";

import "vuetify/dist/vuetify.min.css";
import Vuetify from "vuetify/lib";
Vue.use(Vuetify);
@Component
export default class App extends Vue {}
</script>
<style lang="scss">
#app {
  font-family: -Roboto sans-serif;

  text-align: center;
  color: black;
  height: 100%;
  width: 100%;
  margin: 0 auto;
  a {
    color: white;
  }
}
a {
  text-decoration: none;
  font-weight: bold;
  color: #2c3e50;

  &.router-link-exact-active {
    font-size: 40px;
    text-transform: uppercase;
    font-weight: 200;
    text-decoration: none;
  }
}
</style>
