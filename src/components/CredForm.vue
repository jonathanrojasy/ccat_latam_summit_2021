<template>
  <v-sheet
      class="py-12"
      color="transparent"
  >
    <v-form
        ref="form"
        v-model="valid"
        lazy-validation
    >
      <v-container fluid fill-height>
        <v-col>
          <v-row align="center" justify="center">
            <v-col :cols="$vuetify.breakpoint.xs ? 12 : 10">
              <v-row align="center" justify="center">
                <v-col cols="4">
                  <v-row align="center" justify="center">
                    <v-avatar
                        class="profile"
                        size="100"
                    >
                      <v-img :src="url"></v-img>
                    </v-avatar>
                  </v-row>
                </v-col>
                <v-col cols="8">
                  <v-row align="center" justify="center">
                    <v-file-input
                        accept="image/png, image/jpeg"
                        placeholder="Sube tu foto"
                        @change="Preview_image"
                        v-model="image"
                        dark
                    >
                    </v-file-input>
                  </v-row>
                </v-col>
              </v-row>
            </v-col>
          </v-row>

          <v-row justify="center">
            <v-col :cols="$vuetify.breakpoint.xs ? 12 : 10">
              <v-text-field
                  v-model="name"
                  :counter="28"
                  :rules="nameRules"
                  id="input_nombre"
                  placeholder="Ingresa tu Nombre y Apellido"
                  solo
                  class="text-center"
                  flat
                  style="border-radius: 8px"
                  required
                  single-line
              ></v-text-field>
            </v-col>
          </v-row>

          <v-row justify="center" class="pt-10">
            <v-col :cols="$vuetify.breakpoint.xs ? 12 : 10">
              <v-btn
                  :disabled="!valid"
                  color="red"
                  @click="validate"
                  depressed
                  x-large
                  block
              >
                <span
                    class="white--text font-weight-bold"
                    :class="$vuetify.breakpoint.xs ? 'text-caption' : 'text-h6'"
                >Generar mi credencial</span>
              </v-btn>
            </v-col>
          </v-row>
        </v-col>
      </v-container>
    </v-form>
  </v-sheet>
</template>

<style scoped>
#input_nombre {
  text-align: center;
}
</style>

<script>
export default {
  name: "CredForm",
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
    }
  },
}
</script>