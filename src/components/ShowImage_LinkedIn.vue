<template>
  <div id="credlinkedin" class="pa-0 padre">
    <v-img
        :max-width="$vuetify.breakpoint.xs ? 350 : 600"
        :max-height="$vuetify.breakpoint.xs ? 200 : 350"
        :src="require('@/assets/credenciales/linkedin.png')"
    >
    </v-img>
    <v-form
        class="center-input"
        :class="$vuetify.breakpoint.xs ? 'center-input-2' : 'center-input'"
    >
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
  top: 66%;
  left: 74%;
  transform: translate(-50%, -50%);
  width: 240px;
}
.center-input-2 {
  position: absolute;
  top: 70%;
  left: 71%;
  transform: translate(-50%, -50%);
  width: 150px;
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
.center-image-2 {
  position: absolute;
  top: 50%;
  left: 73.2%;
  transform: translate(-50%, -50%);
}
</style>