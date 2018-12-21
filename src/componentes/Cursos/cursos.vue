<template>
  <v-layout app justify-center>
    <v-flex>
      <v-card>
        <v-container>
          <v-layout>
            <v-flex xs6 right>
              <v-text-field
                prepend-icon="search"
                label="Buscar Curso"
                v-model="buscar"
              ></v-text-field>
            </v-flex>
            <v-flex xs12> </v-flex>
          </v-layout>
        </v-container>
        <CuadroImagenes :data="BusquedaCursos"> </CuadroImagenes>
      </v-card>
    </v-flex>
  </v-layout>
</template>

<script>
import CuadroImagenes from "./cuadroImagenes.vue";
export default {
  components: { CuadroImagenes },
  data() {
    return {
      buscar: "",
      data: [
        {
          Nombre: "Introducción a Arduino",
          Precio: 60,
          Descripcion: "Crea prototipos electrónicos de manera sencilla",
          src_imagen:
            "https://fabricadigital.org/wp-content/uploads/arduinouno_back_1.jpg",
          categoria: [
            "Sistemas Embebidos",
            "Ingenería",
            "Desarrollo de Hardware",
            "Electrónica",
            "Programación"
          ]
        },
        {
          Nombre: "Introducción a Raspberry Pi",
          Precio: 120,
          Descripcion:
            "Desarrolla proyectos de mayor alcance usando este miniordenador",
          src_imagen:
            "https://upload.wikimedia.org/wikipedia/commons/b/b4/Raspberry_Pi_3_Model_B.png",
          categoria: [
            "Sistemas Emebebidos",
            "Ingenería",
            "Desarrollo de Hardware",
            "Linux",
            "Electrónica"
          ]
        },
        {
          Nombre: "Desarrollo Web",
          Precio: 120,
          Descripcion:
            "Desarrolla tu propia página web y aplicaciones usando el stack MEVN",
          src_imagen: "https://i.ytimg.com/vi/ARIzrNwA5HQ/maxresdefault.jpg",
          categoria: [
            "Desarrollo Web",
            "Javascript",
            "Framework Frontend",
            "Mongodb"
          ]
        }
      ]
    };
  },
  methods: {
    busqueda(buscar) {
      this.data = this.data.filter(post => {
        return post.title.match(buscar);
      });
    }
  },
  computed: {
    BusquedaCursos: function() {
      return this.data.filter(cursos => {
        return cursos.Nombre.toLowerCase().includes(this.buscar.toLowerCase());
      });
    },
    filteredList() {
      return this.data.filter(post => {
        return post.Nombre.toLowerCase().includes(this.buscar);
      });
    }
  }
};
</script>
