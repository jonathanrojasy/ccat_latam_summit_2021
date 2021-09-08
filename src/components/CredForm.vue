<template>
  <v-sheet
      :class="$vuetify.breakpoint.xs ? 'py-6' : 'py-12'"
      color="transparent"
  >
    <v-form
        ref="form"
        v-model="valid"
        lazy-validation
    >
      <v-container fluid fill-height>
        <v-col :cols="$vuetify.breakpoint.xs ? 0 : 1"></v-col>
        <v-col :cols="$vuetify.breakpoint.xs ? 12 : 12">

          <v-row align="center" justify="center" no-gutters>
            <sheetSpacer :height="$vuetify.breakpoint.xs ? 150 : 112"/>
          </v-row>

          <v-row align="center" justify="center" no-gutters>
            <v-container fluid fill-height class="py-2">
              <v-col :cols="$vuetify.breakpoint.xs ? 1 : 1">
                <v-file-input
                    accept="image/png, image/jpeg"
                    placeholder="Sube tu foto"
                    @change="Preview_image"
                    v-model="image"
                    dark
                    hide-details
                    hide-input
                >
                </v-file-input>
              </v-col>
              <v-col :cols="$vuetify.breakpoint.xs ? 10 : 10">
                <v-row align="center" justify="center">
                  <v-col>
                    <v-row align="center" class="center-avatar">
                      <v-avatar
                          class="profile"
                          size="108"
                      >
                        <v-img :src="url"></v-img>
                      </v-avatar>
                    </v-row>
                  </v-col>
                </v-row>
              </v-col>
            </v-container>
          </v-row>

          <v-row align="center" justify="center" no-gutters>
            <v-col :cols="$vuetify.breakpoint.xs ? 10 : 10">
              <v-text-field
                  v-model="name"
                  :counter="28"
                  :rules="nameRules"
                  placeholder="Nombre y Apellido"
                  solo
                  class="centered-input font-weight-bold text-caption"
                  flat
                  rounded
                  dense
                  required
                  single-line
                  hide-details
              ></v-text-field>
            </v-col>
          </v-row>

          <v-row align="center" justify="center" no-gutters>
            <sheetSpacer :height="$vuetify.breakpoint.xs ? 60 : 50"/>
          </v-row>

          <v-row align="center" justify="center" no-gutters>
            <v-col :cols="$vuetify.breakpoint.xs ? 8 : 12">
              <v-container fluid fill-height style="justify-content: center;padding: 0">
                <v-btn
                    :disabled="!valid"
                    color="#D85551"
                    @click="validate"
                    depressed
                    rounded
                >
                <span
                    class="white--text"
                    :class="$vuetify.breakpoint.xs ? 'text-caption font-weight-light' : 'text-subtitle-2'"
                >Generar credencial</span>
                </v-btn>
              </v-container>
            </v-col>
          </v-row>
        </v-col>
        <v-col :cols="$vuetify.breakpoint.xs ? 0 : 1"></v-col>
      </v-container>
    </v-form>
  </v-sheet>
</template>

<style scoped>
.centered-input >>> input {
  text-align: center;
}
.center-avatar {
  position: relative;
  top: 81%;
  left: 21%;
}
</style>

<script>
import sheetSpacer from "./sheetSpacer";
export default {
  name: "CredForm",
  components:{
    sheetSpacer
  },
  data: () => ({
    valid: true,
    url: null,
    image: null,
    name: '',
    nameRules: [
      v => !!v || 'Ingrese su nombre por favor.',
      v => (v && (v.length >= 2)) || 'Su nombre debe contener por lo menos 2 caracteres.',
      v => (v && (v.length <= 28)) || 'Su nombre debe contener a lo más 30 caracteres.',
    ],
  }),

  methods: {
    validate () {
      if (this.$refs.form.validate() && this.name.length < 28){
        this.$router.push({name: 'CreateCredential', params: {name: this.name, url: this.url}})
      }
    },
    Preview_image() {
      if(this.image){
        this.url= URL.createObjectURL(this.image)
      }
    },
  },
}
</script>