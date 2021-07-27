<template>
  <v-footer
      dark
      padless
  >
    <v-card
        class="flex"
        flat
        tile
    >
      <v-card-text
          class="text-center pa-0"
      >
        <v-card
            class="d-flex justify-space-around"
            flat
            tile
            :height="$vuetify.breakpoint.xs ? 60 : 120"
            color="#FFFFFC"
        >
          <v-card
              v-for="item in sponsors"
              :key="item.id"
              class="align-self-center"
              flat
              tile
              width="110"
              color="transparent"
          >
            <v-btn
                :href="item.link"
                target="_blank"
                color="transparent"
                text
            >
              <v-img
                  class="pa-0"
                  :src="item.path()"
                  :width="$vuetify.breakpoint.xs ? 30 : 90"
              ></v-img>
            </v-btn>
          </v-card>
        </v-card>
      </v-card-text>
      <v-card-text
          class="text-center"
          style="background-color: #231F20"
      >
        <v-row align="center">
          <v-col>
            <v-btn
                v-for="red in redes"
                :key="red.id"
                class="mx-4"
                dark
                icon
                target="_blank"
            >
              <v-icon size="28px">
                {{ red.icon }}
              </v-icon>
            </v-btn>
          </v-col>
        </v-row>
      </v-card-text>
    </v-card>
  </v-footer>
</template>

<script>
export default {
  name: "Footer",
  data: () => ({
    alto: 150,
    ancho: 200,
    sponsors: [
      {id: "s1", name: 'UNI', path: () => {return require('@/assets/logo_uni_transparente.png');}, link: 'https://www.uni.edu.pe/'},
      {id: "s2", name: 'CODE', path: () => {return require('@/assets/code.png');}, link: 'http://codewebpage.herokuapp.com'},
      {id: "s3", name: 'CCAT', path: () => {return require('@/assets/logo_ccat_azul.png');}, link: 'https://www.facebook.com/ccat.pe'},
      {id: "s4", name: 'Revista Competitividad', path: () => {return require('@/assets/rv.png');}, link: 'https://revistacompetitividad.com'},
      {id: "s5", name: 'Cultura y Desarrollo Humano', path: () => {return require('@/assets/cdh.png');}, link: 'https://www.facebook.com/DireccionDeCulturaCCAT'},
    ],
    redes: [
      {id: "r1", icon: 'mdi-facebook', link: 'https://www.facebook.com/ccat.pe'},
      {id: "r2", icon: 'mdi-linkedin', link: 'https://www.linkedin.com/company/ccatpe/'},
      {id: "r3", icon: 'mdi-youtube', link: 'https://www.youtube.com/user/CCATFIIS'},
      {id: "r4", icon: 'mdi-instagram', link: 'https://www.instagram.com/ccat.pe/'},
    ],
  }),
}
</script>

<style scoped>
.btn-sponsors:focus {
  opacity: 0.25 !important;
}
</style>