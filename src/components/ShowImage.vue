<template>
  <div id="credhistorias" class="pa-0">
    <v-img
        max-width="350"
        max-height="650"
        :src="require('@/assets/credenciales/historias.png')"
    >
    </v-img>
    <span
        class="center-input font-weight-bold"
    > {{name}}</span>
    <v-avatar
        class="profile center-image"
        size="125"
    >
      <v-img :src="url"></v-img>
    </v-avatar>
  </div>
</template>

<script>
export default {
  name: "ShowImage",
  props:{
    name: String,
    url: String,
  },
}
</script>

<style scoped>
.center-input {
  position: absolute;
  top: 69%;
  left: 50%;
  transform: translate(-50%, -50%);
  text-align: center;
  font-family: Monserrat;
}

.center-image {
  position: absolute;
  top: 55.6%;
  left: 50%;
  transform: translate(-50%, -50%);
}
</style>