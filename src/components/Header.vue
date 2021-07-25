<template>
  <v-toolbar
      dark
      color="transparent"
      flat
      prominent
  >
    <v-toolbar-title class="ps-4 pt-4">
      <v-img
          :src="require('@/assets/CCAT-LogoBlanco.png')"
          max-height="80"
          max-width="80"
          contain
      ></v-img>
    </v-toolbar-title>
  </v-toolbar>
</template>

<script>
export default {
  name: "Header"
}
</script>

<style scoped>

</style>