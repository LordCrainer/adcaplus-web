<template>
  <v-container grid-list-xl>
    <v-layout wrap row justify-center align-center>
      <v-flex xs12 sm6 md6 v-for="dato in data" :key="dato.Nombre">
        <v-hover>
          <v-card
            slot-scope="{
              hover,
              active,
              toggle
            }"
            class="mx-auto"
            max-width="350"
            height="350"
            :class="`elevation-${hover ? 10 : 4}`"
          >
            <v-img contain :aspect-ratio="16 / 9" :src="dato.src_imagen">
              <v-layout align-center justify-center row>
                <v-flex xs12>
                  <v-card color="rgba(25, 25, 25, 0.8)">
                    <v-card-text
                      class="text-xs-center headline orange--text  font-weight-black"
                      width="100%"
                    >
                      <span>{{ dato.Nombre }}</span>
                    </v-card-text>
                  </v-card>
                </v-flex>
              </v-layout>
              <v-expand-transition>
                <router-link
                  v-if="hover"
                  class="d-flex transition-fast-in-fast-out blue lighten-1 v-card--reveal display-3 black--text"
                  style="height: 100%; text-decoration: none;"
                  to="/"
                >
                  <v-container>
                    <v-btn icon fab color="yellow"
                      ><v-icon large>info</v-icon></v-btn
                    ></v-container
                  >
                </router-link>
              </v-expand-transition>
            </v-img>
            <v-card-text class="pt-4" style="position: relative;">
              <v-btn
                absolute
                color="green"
                class="white--text"
                fab
                large
                right
                top
                style="z-index: 0;"
              >
                <v-icon>school</v-icon>
              </v-btn>

              <div></div>
            </v-card-text>
            <v-card-text class="font-weight-light title mb-2 my-2">
              {{ dato.Descripcion }}
            </v-card-text>
          </v-card>
        </v-hover>
      </v-flex>
    </v-layout>
  </v-container>
</template>
<style>
.v-card--reveal {
  align-items: center;
  top: 0;
  justify-content: center;
  opacity: 0.7;
  position: absolute;
  width: 100%;
}
</style>
<script>
export default {
  props: ["data"]
};
</script>
