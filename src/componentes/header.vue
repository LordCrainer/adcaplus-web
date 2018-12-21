<style scoped>
#list {
  background-color: rgba(255, 255, 255, 0.95);
}
</style>

<template>
  <nav v-scroll="onScroll">
    <v-navigation-drawer
      id="list"
      app
      temporary
      hide-overlay
      fixed
      disable-resize-watcher
      v-model="drawer_flag"
      right
    >
      <List :items="menus" @epath="nombreRuta($event);"></List>
      <v-btn
        fixed
        bottom
        right
        fab
        dark
        color="blue"
        @click.stop="drawer_flag = !drawer_flag;"
      >
        <v-icon>exit_to_app</v-icon>
      </v-btn>
    </v-navigation-drawer>
    <v-toolbar
      app
      fixed
      :dark="offsetTop < 30 ? true : false"
      class="elevation-8 "
      :color="color_toolbar"
    >
      <router-link to="/">
        <img :src="src_logo" alt="alt" width="70px" height="70px" />
      </router-link>
      <v-spacer></v-spacer>
      <v-toolbar-title
        :class="color_text"
        class="font-weight-black"
        style="font-size: 30px;"
      >
        ADCAPLUS
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items class="hidden-sm-and-down">
        <v-btn
          id="botonBar"
          flat
          v-for="menu in menus"
          :key="menu.nombre"
          :to="menu.ruta"
          class="font-weight-black caption"
          :color="color_text.split('--')[0]"
        >
          {{ menu.nombre }}
        </v-btn>
        <!--
          <Navbar
            @epath="nombreRuta($event);"
            :menus="menus"
            :clases="color_text"
          ></Navbar>
        -->
      </v-toolbar-items>
      <v-btn
        flat
        icon
        :color="color_text.split('--')[0]"
        class="hidden-md-and-up"
        @click.stop="drawer_flag = !drawer_flag;"
      >
        <v-icon large>more_vert</v-icon>
      </v-btn>
    </v-toolbar>
  </nav>
</template>

<script>
import Navbar from "./navbar.vue";
import List from "./UI/list.vue";
//import pdfvue from "./inicio/pdf.vue";
//import PDF from "jspdf";
export default {
  props: ["menus"],
  components: {
    Navbar,
    List
  },
  data() {
    return {
      src_logo:
        "https://uploads.codesandbox.io/uploads/user/17fffd86-3ee1-4ca9-abc0-4e76a2cb57f0/3C31-logo3.png",
      offsetTop: 0,
      color_toolbar: "rgba(255, 255, 255, 0.9)",
      color_text: "black--text",
      height_toolbar: "70px",
      drawer_flag: false,
      color: "black",
      tab: null,

      text:
        "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat."
    };
  },
  methods: {
    onScroll(e) {
      this.offsetTop = window.pageYOffset || document.documentElement.scrollTop;
      if (this.offsetTop > 30) {
        this.color_toolbar = "rgba(50, 50, 50, 0.8)";
        this.height_toolbar = "70px";
        this.color_text = "white--text";
      } else {
        this.color_toolbar = "rgba(255, 255, 255, 0.9)";
        this.height_toolbar = "70px";
        this.color_text = "black--text";
      }
    },
    nombreRuta(ruta) {
      this.$emit("epath", ruta);
    }
  }
};
</script>
