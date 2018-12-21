<template>
  <v-parallax :src="srcImagen" :height="altura">
    <v-layout align-center justify-center>
      <div>
        <h1 v-if="comparar(item)" style="font-size: 50px; color: black;">
          {{ item }}
        </h1>
      </div>
    </v-layout>
  </v-parallax>
</template>
<script>
export default {
  props: ["item", "srcImagen"],
  data() {
    return {
      altura: 350
    };
  },
  created() {
    this.comparar(this.item);
  },
  methods: {
    comparar(item) {
      if (this.item !== undefined) {
        if (item !== "INICIO" && item !== "/") {
          this.altura = 400;
          return true;
        } else {
          this.altura = 350;
          return true;
        }
      }
    }
  }
};
</script>
