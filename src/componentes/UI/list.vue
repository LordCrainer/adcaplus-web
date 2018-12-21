<style scoped>
.border_hover:hover {
  border-left: 10px solid rgba(15, 15, 15, 0.5);
  background-color: rgba(15, 15, 15, 0.1);
  color: black;
  font-weight: bold;
}
.v-list {
  background-color: rgba(255, 255, 255, 0);
}
</style>

<template>
  <v-list dense style="back">
    <v-list-tile
      class="border_hover"
      v-for="(menu, index) in items"
      :key="index"
      @click="nombreRuta(menu.ruta);"
      :to="menu.ruta"
      ripple
    >
      <v-list-tile-title class="font-weight-bolder">
        <h3>{{ menu.nombre }}</h3></v-list-tile-title
      >
    </v-list-tile>
  </v-list>
</template>

<script>
export default {
  props: ["items", "path"],
  data() {
    return {
      tab: null
      //:to="path[index]"
    };
  },
  methods: {
    nombreRuta(ruta) {
      this.$emit("epath", ruta);
    }
  }
};
</script>
