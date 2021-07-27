<template>
  <v-toolbar
      dark
      color="transparent"
      flat
      prominent
  >
    <v-card
        class="flex"
        color="transparent"
        flat
        tile
    >
      <v-card-title>
        <v-img
            :src="require('@/assets/CCAT-LogoBlanco.png')"
            max-height="80"
            max-width="80"
            contain
        ></v-img>
        <v-spacer></v-spacer>
        <v-img
            :src="require('@/assets/logo_uni_transparente.png')"
            max-height="80"
            max-width="80"
            contain
        ></v-img>
      </v-card-title>
    </v-card>
  </v-toolbar>
</template>

<script>
export default {
  name: "Header"
}
</script>

<style scoped>

</style>