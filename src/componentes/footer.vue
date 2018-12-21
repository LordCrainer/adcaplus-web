<template>
  <v-footer dark height="auto">
    <v-card
      width="100%"
      flat
      tile
      color="rgb(16, 60, 145)"
      class="white--text text-xs-center"
    >
      <v-card-text>
        <v-btn v-for="icon in icons" :key="icon" class="mx-2 white--text" icon>
          <v-icon size="24px">{{ icon }}</v-icon>
        </v-btn>
      </v-card-text>

      <v-card-text class="white--text pt-0">
        <v-container grid-list-xl>
          <v-layout wrap justify-space-around align-center>
            <v-flex xs6 sm3 md3 class="mb-3">
              <v-layout column justify-center align-center>
                <h3 class="orange--text">PRINCIPAL</h3>
                <router-link
                  v-for="menu in menus"
                  :key="menu.nombre"
                  :to="menu.ruta"
                >
                  <v-btn flat round class="my-0">{{ menu.nombre }} </v-btn>
                </router-link>
              </v-layout>
            </v-flex>
          </v-layout>
        </v-container>
      </v-card-text>

      <v-divider></v-divider>

      <v-card-text class="white--text">
        &copy;2018 — <strong>ADCAPLUS</strong>
      </v-card-text>
    </v-card>
  </v-footer>
</template>
<script>
export default {
  props: ["menus"],
  data() {
    return {
      icons: [
        "fab facebook-square",
        "fab fa-twitter",
        "fab fa-google-plus",
        "fab fa-linkedin",
        "fab fa-instagram"
      ],
      text:
        "Phasellus feugiat arcu sapien, et iaculis ipsum elementum sit amet. Mauris cursus commodo interdum. Praesent ut risus eget metus luctus accumsan id ultrices nunc. Sed at orci sed massa consectetur dignissim a sit amet dui. Duis commodo vitae velit et faucibus. Morbi vehicula lacinia malesuada. Nulla placerat augue vel ipsum ultrices, cursus iaculis dui sollicitudin. Vestibulum eu ipsum vel diam elementum tempor vel ut orci. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus."
    };
  }
};
</script>
