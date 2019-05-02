<template>
  <v-app id="app">
    <v-toolbar color="blue-grey" dark fixed app clipped-right>
      <v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon>
      <v-toolbar-title>App</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items class="hidden-sm-and-down">
        <v-btn flat to="/">Home</v-btn>
        <v-btn flat to="/about">About</v-btn>
      </v-toolbar-items>
    </v-toolbar>
    <v-navigation-drawer v-model="drawer" fixed app>
      <v-list dense>
        <v-list-tile>
          <v-list-tile-content>
            <v-list-tile-title>Menu</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
        <v-list-tile @click.stop="" to="/">
          <v-list-tile-action>
            <v-icon>home</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title>Home</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
        <v-list-tile @click.stop="" to="/about">
          <v-list-tile-action>
            <v-icon>info</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title>About</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-navigation-drawer v-model="left" temporary fixed></v-navigation-drawer>
    <v-content>
      <v-container fluid fill-height>
        <v-layout justify-center align-center>
          <v-flex shrink>
            <v-tooltip right>
              <template v-slot:activator="{ on }">
                <router-view></router-view>
              </template>
            </v-tooltip>
          </v-flex>
        </v-layout>
      </v-container>
    </v-content>
    <v-navigation-drawer v-model="right" right temporary fixed></v-navigation-drawer>
    <v-footer color="blue-grey" class="white--text" app>
      <span>Ninjaa</span>
      <v-spacer></v-spacer>
      <span>&copy; 2019</span>
    </v-footer>
  </v-app>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  data: () => ({
    drawer: null,
    drawerRight: null,
    right: false,
    left: false
  }),
  props: {
    source: String
  },
  components: {}
}
</script>

<style>
.v-btn a {
  text-decoration: none !important;
}
</style>
