<style>
.v-carousel__next button,
.v-carousel__prev button {
  background-color: rgba(0, 0, 0, 0.65);
}
.v-carousel__controls .v-item-group .v-btn--active .v-btn__content i {
  border-radius: 50%;
  background-color: rgba(255, 255, 255, 1);
}
.v-carousel__controls .v-item-group .v-btn--active {
  height: 30px;
  width: 30px;
  background-color: rgba(255, 255, 255, 0.1);
}
</style>

<template>
  <v-carousel height="550">
    <v-carousel-item v-for="(item, i) in items" :key="i" :src="item.src">
      <!--
        <v-container fill-height grid-list-xl>
          <v-layout align-end justify-center row>
            <v-flex md6 sm6 xs12>
              <v-card color="rgba(102, 102, 102, 0.9)">
                <v-card-text class="text-xs-center">
                  <span class="display-1 white--text  font-weight-black">{{
                    item.text
                  }}</span>
                </v-card-text>

                <v-container fill-height>
                  <v-layout row align-center justify-center>
                    <v-flex>
                      <v-btn round color="primary" dark>ENTRAR</v-btn>
                    </v-flex>
                    <v-flex>
                      <v-btn round outline color="white " dark>Servicios </v-btn>
                    </v-flex>
                  </v-layout>
                </v-container>
              </v-card>
            </v-flex>
          </v-layout>
        </v-container>
      -->
    </v-carousel-item>
  </v-carousel>
</template>

<script>
export default {
  data() {
    //v-btn v-btn--icon v-btn--small theme--dark v-carousel__controls__item
    return {
      //class="v-btn v-btn--active v-btn--icon v-btn--small theme--dark v-carousel__controls__item"
      items: [
        {
          text: "TRABAJO EN EQUIPO",
          src:
            "https://www.efeblog.com/wp-content/uploads/2018/05/trabajo-en-equipo.jpg"
        },
        {
          text: "APRENDIZAJE",
          src: "http://www.yeahiptv.com/uploads/contact-us.jpeg"
        },
        {
          text: "DESARROLLO",
          src:
            "https://whitepapers.em360tech.com/wp-content/uploads/Nvidia-Telco.jpeg"
        }
      ]
    };
  }
};
</script>
