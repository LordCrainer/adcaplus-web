<template>
  <v-app style="background-color: transparent; margin:0px;  min-width:250px;">
    <Headerw :menus="menu_principal"></Headerw>

    <router-view name="carousel"></router-view>

    <Parallax
      :item="rutaActual"
      srcImagen="https://www.tendencias.kpmg.es/wp-content/uploads/2018/05/GettyImages-672310452-e1525335107388.jpg"
    ></Parallax>

    <router-view @epath="nombreRuta($event);"></router-view>

    <FooterW :menus="menu_principal"></FooterW>
  </v-app>
</template>

<script>
import Headerw from "./componentes/header.vue";
import FooterW from "./componentes/footer.vue";
import Parallax from "./componentes/UI/parallax.vue";
//import Carusel from "./componentes/Inicio/carusel.vue";
//import Hosting from "./componentes/hosting/hostings.vue";
//import datePicker from "./componentes/date-picker.vue";
//import subtab from "./componentes/subtab.vue";
export default {
  components: {
    Headerw,
    FooterW,
    Parallax
  },
  data() {
    return {
      rutaActual: "",
      menu_principal: [
        {
          ruta: "/",
          nombre: "Inicio"
        },
        {
          ruta: "/cursos",
          nombre: "Cursos"
        },
        {
          ruta: "/blog",
          nombre: "Blog"
        },
        {
          ruta: "/nosotros",
          nombre: "Nosotros"
        },
        {
          ruta: "/contacto",
          nombre: "Contacto"
        }
      ]
    };
  },
  created() {
    this.getPath();
  },
  watch: {
    $route() {
      this.rutaActual = this.$route.name;
      //.path.toUpperCase().split("/")[1]
    }
  },
  methods: {
    getPath() {
      this.rutaActual = this.$route.name;
    },
    nombreRuta(ruta) {
      this.rutaActual = ruta;
    }
  }
};
</script>

<style>
@import "https://cdnjs.cloudflare.com/ajax/libs/animate.css/3.7.0/animate.min.css";
body {
  color: #fff;
  background: white;
  background: linear-gradient(
    135deg,
    rgb(16, 60, 145) 20%,
    rgba(248, 172, 0, 0.1) 20%,
    rgba(248, 172, 0, 0.1) 75%,
    rgb(16, 60, 145) 75%
  );
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
    Oxygen-Sans, Ubuntu, Cantarell, "Helvetica Neue", Helvetica, Arial,
    sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

/*h1,
h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}*/
.page {
  position: fixed;
  width: inherit;
}
</style>
