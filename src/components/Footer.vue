<template>
  <v-footer
      padless
      color="indigo darken-1"
  >
    <v-card
        color="indigo darken-4"
        flat
        tile
    >
      <v-card-title>
        <v-img
            :src="require('@/assets/CCAT-LogoBlanco.png')"
            max-height="60"
            max-width="60"
            contain
        ></v-img>
      </v-card-title>
    </v-card>
    <v-card
        flat
        tile
        color="transparent"
        class="ml-auto"
    >
      <v-card-title>
        <v-btn
            v-for="red in redes"
            :href="red.link"
            target="_blank"
            :key="red.id"
            class="mx-4"
            dark
            icon
        >
          <v-icon size="24px">
            {{ red.icon }}
          </v-icon>
        </v-btn>
      </v-card-title>
    </v-card>
    <v-card
        flat
        tile
        color="transparent"
        class="ml-auto"
    >
      <v-spacer></v-spacer>
      <v-card-title>
        <v-btn
            v-for="red in redes"
            :href="red.link"
            target="_blank"
            :key="red.id"
            class="mx-4"
            dark
            icon
        >
          <v-icon size="24px">
            {{ red.icon }}
          </v-icon>
        </v-btn>
      </v-card-title>
    </v-card>
  </v-footer>
</template>

<script>
export default {
  name: "Footer",
  data: () => ({
    redes: [
      {id: 1, icon: 'mdi-facebook', link: 'https://www.facebook.com/ccat.pe'},
      {id: 2, icon: 'mdi-linkedin', link: 'https://www.linkedin.com/company/ccatpe/'},
      {id: 3, icon: 'mdi-youtube', link: 'https://www.youtube.com/user/CCATFIIS'},
      {id: 4, icon: 'mdi-instagram', link: 'https://www.instagram.com/ccat.pe/'},
    ],
  }),
}
</script>

<style scoped>

</style>