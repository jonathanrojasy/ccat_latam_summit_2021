<template>
  <div id="capcred" class="pa-2 padre">
    <v-img
        :src="require('@/assets/Fondo-credencial.png')"
    >
    </v-img>
    <v-form class="center-input">
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
    <v-avatar
        class="profile center-image"
        size="170"
    >
      <v-img :src="url==null? require('@/assets/foto_icon.png') : url"></v-img>
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
  top: 45%;
  left: 50%;
  transform: translate(-50%, -50%);
}
.center-image {
  position: absolute;
  top: 67%;
  left: 50%;
  transform: translate(-50%, -50%);
}
</style>