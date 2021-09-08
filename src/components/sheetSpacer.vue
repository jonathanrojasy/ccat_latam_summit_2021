<template>
  <v-container fluid fill-height>
    <v-sheet
        :height="height"
    ></v-sheet>
  </v-container>
</template>

<script>
export default {
  name: "sheetSpacer",
  props:{height: Number}
}
</script>

<style scoped>

</style>