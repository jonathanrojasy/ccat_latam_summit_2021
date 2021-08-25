<template>
  <div id="credlinkedin" class="pa-2 padre">
    <v-img
        max-width="600"
        max-height="350"
        :src="require('@/assets/credenciales/linkedin.png')"
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
        size="152"
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
  left: 74%;
  transform: translate(-50%, -50%);
  width: 240px;
}
.center-input >>> input {
  text-align: center;
}
.center-image {
  position: absolute;
  top: 42%;
  left: 73.4%;
  transform: translate(-50%, -50%);
}
</style>