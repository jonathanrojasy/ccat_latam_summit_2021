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
      <v-card-title
          class="pink lighten-3 pa-0"
      >
        <v-sheet
            height="100"
            width="100"
            color="red darken-1"
            class="fill-height container--fluid"
        >
          <v-col>
            <v-row class="justify-center pt-2">
              <v-img
                  :src="require('@/assets/CCAT-LogoBlanco.png')"
                  max-width="90"
              ></v-img>
            </v-row>
          </v-col>
        </v-sheet>

        <v-spacer></v-spacer>

        <v-btn
            v-for="sponsor in sponsors"
            :key="sponsor.id"
            class="px-6"
            :href="sponsor.link"
            plain
        >
          <v-img
              :src="sponsor.path()"
              max-width="80"
          ></v-img>
        </v-btn>
      </v-card-title>
      <v-card-text
          class="text-center">
        <v-btn
            v-for="red in redes"
            :key="red.id"
            class="mx-4"
            dark
            icon
        >
          <v-icon size="24px">
            {{ red.icon }}
          </v-icon>
        </v-btn>
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
      {id: "s1", name: 'CODE', path: () => {return require('@/assets/code.png');}, link: 'http://codewebpage.herokuapp.com'},
      {id: "s2", name: 'Revista Competitividad', path: () => {return require('@/assets/rv.png');}, link: 'https://revistacompetitividad.com'},
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

</style>