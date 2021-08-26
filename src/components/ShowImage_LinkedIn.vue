<template>
  <div id="credlinkedin" class="pa-0">
    <v-img
        :max-width="$vuetify.breakpoint.xs ? 350 : 600"
        :max-height="$vuetify.breakpoint.xs ? 200 : 350"
        :src="require('@/assets/credenciales/linkedin.png')"
    >
    </v-img>
    <span
        class="center-input font-weight-bold"
        :class="$vuetify.breakpoint.xs ? 'center-input-2' : 'center-input'"
    >
      {{name}}
    </span>
    <v-avatar
        class="profile"
        :class="$vuetify.breakpoint.xs ? 'center-image-2' : 'center-image'"
        :size="$vuetify.breakpoint.xs ? 85 : 152"
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
  top: 66.5%;
  left: 74%;
  transform: translate(-50%, -50%);
  width: 240px;
  text-align: center;
  font-family: Monserrat;
}
.center-input-2 {
  position: absolute;
  top: 70%;
  left: 71%;
  transform: translate(-50%, -50%);
  width: 150px;
  text-align: center;
  font-family: Monserrat;
}
.center-image {
  position: absolute;
  top: 41.5%;
  left: 73.4%;
  transform: translate(-50%, -50%);
}
.center-image-2 {
  position: absolute;
  top: 50%;
  left: 73.2%;
  transform: translate(-50%, -50%);
}
</style>