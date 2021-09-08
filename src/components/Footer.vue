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
            class="d-flex flex-wrap justify-space-around"
            flat
            tile
            :height="$vuetify.breakpoint.width < 1000 ? ($vuetify.breakpoint.width < 500 ? 400 : 240) : 120"
            color="#FFFFFC"
        >
          <v-card
              v-for="item in sponsors"
              :key="item.id"
              class="align-self-center"
              flat
              tile
              width="250"
              color="transparent"
              :class="$vuetify.breakpoint.xs ? 'pa-8' : 'pa-0'"
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
                  :max-width="$vuetify.breakpoint.xs ? (3*item.width/4) : item.width"
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
                :href="red.link"
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
      {id: "s1", name: 'CODE', width: 200,
        path: () => {return require('@/assets/sponsors/code.png');},
        link: 'http://codewebpage.herokuapp.com'},
      {id: "s2", name: 'CCAT', width: 110,
        path: () => {return require('@/assets/sponsors/logo_ccat_azul.png');},
        link: 'https://www.facebook.com/ccat.pe'},
      {id: "s3", name: 'Dirección de Cultura y Desarrollo Humano', width: 110,
        path: () => {return require('@/assets/sponsors/cdh.jpg');},
        link: 'https://www.facebook.com/DireccionDeCulturaCCAT'},
      {id: "s4", name: 'Revista Competitividad', width: 200,
        path: () => {return require('@/assets/sponsors/rv.png');},
        link: 'https://revistacompetitividad.com'},
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
