<template>
  <div id="downcredhistorias" class="pa-0">
    <v-img
        max-width="1080"
        max-height="1920"
        :src="require('@/assets/credenciales/historias.png')"
    >
    </v-img>
    <span class="center-input font-weight-bold">{{name}}</span>

    <v-avatar
        class="profile center-image"
        size="361"
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
  top: 64.58%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 666px;
  text-align: center;
  font-size: 55px;
  font-family: Monserrat;
}
.center-image {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
</style>