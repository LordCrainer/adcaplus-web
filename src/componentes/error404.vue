<template>
  <v-layout align-center justify-center>
    <v-flex xs12 sm8>
      <v-card>
        <v-img
          class="white--text"
          height="200px"
          src="http://spootmedia.com/wp-content/uploads/2018/06/443809727.jpg"
        >
        </v-img>
        <v-card-text>
          <div>
            <h1 class="grey--text">PAGINA NO ENCONTRADA</h1>
            <slot> </slot> <br />
          </div>
        </v-card-text>
        <v-card-actions>
          <router-link to="/">
            <v-btn color="primary"> VOLVER AL INICIO </v-btn></router-link
          >
        </v-card-actions>
      </v-card>
    </v-flex>
  </v-layout>
</template>
<script>
export default {
  created() {
    this.nombreRuta();
  },
  methods: {
    nombreRuta() {
      this.$emit("epath", "ERROR 404");
    }
  }
};
</script>
