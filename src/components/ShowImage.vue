<template>
  <div>
    <v-img
        :src="require('@/assets/Fondo-credencial.png')"
    >
    </v-img>
    <v-form class="centered">
      <v-text-field
          :value="name"
          style="text-align: center"
          readonly
          flat
          dense
          solo
      >
      </v-text-field>
    </v-form>
  </div>
</template>

<script>
export default {
  name: "ShowImage",
  props:{
    name: String,
  },
}
</script>

<style scoped>
.centered {
  position: absolute;
  top: 45%;
  left: 50%;
  transform: translate(-50%, -50%);
}
</style>