<template>
  <v-carousel hide-delimiters height="200" class="comentario">
    <v-carousel-item v-for="(data, i) in datos" :key="i">
      <v-layout align-center column justify-center fill-height>
        <h1 class="headline font-weight-bold mb-3 white--text">
          {{ data.titulo }}
        </h1>
        <h3 class="subheading white--text">{{ data.text }}</h3>
      </v-layout>
    </v-carousel-item>
  </v-carousel>
</template>
<script>
export default {
  data() {
    return {
      datos: [
        {
          src: "https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg",
          titulo: "Aprende, Desarrolla y Capacita",
          text: "Son 3 acciones que cada persona debería de hacer"
        },
        {
          src: "https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg",
          titulo: "Aprende y Crea para el Futuro",
          text:
            "Adquiere conocimientos, desarróllalo y construye un mundo mejor"
        },
        {
          src: "https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg",
          titulo: "El conocimiento se vuelve ineficaz sino se lo aplica",
          text: ""
        }
      ]
    };
  }
};
</script>
<style scoped>
.comentario {
  color: #fff;
  background: #949c4e;
  background: linear-gradient(
    135deg,
    rgba(248, 172, 0, 1) 15%,
    rgba(16, 60, 145, 1) 15%,
    rgba(16, 90, 185, 1) 85%,
    rgba(248, 172, 0, 1) 85%
  );
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
    Oxygen-Sans, Ubuntu, Cantarell, "Helvetica Neue", Helvetica, Arial,
    sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
