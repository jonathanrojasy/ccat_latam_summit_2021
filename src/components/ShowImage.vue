<template>
  <div id="credhistorias" class="pa-2 padre">
    <v-img
        max-width="350"
        max-height="650"
        :src="require('@/assets/credenciales/historias.png')"
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
          hide-details
      >
      </v-text-field>
    </v-form>
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
  top: 66%;
  left: 50%;
  transform: translate(-50%, -50%);
  height: 50px;
  width: 220px;
}
.center-input >>> input {
  text-align: center;
}
.center-image {
  position: absolute;
  top: 52.2%;
  left: 50%;
  transform: translate(-50%, -50%);
}
</style>