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
          <v-row justify="center">
            <v-col :cols="$vuetify.breakpoint.xs ? 12 : 10">
              <v-text-field
                  v-model="name"
                  :counter="20"
                  :rules="nameRules"
                  placeholder="Ingresa tu Nombre y Apellido"
                  solo
                  flat
                  style="border-radius: 8px"
                  required
              ></v-text-field>
            </v-col>
          </v-row>

          <v-row align="center" justify="center">
            <v-col :cols="$vuetify.breakpoint.xs ? 12 : 10">
              <v-row align="center" justify="center">
                <v-col cols="4">
                  <v-row align="center" justify="center">
                    <v-avatar
                        class="profile"
                        size="100"
                    >
                      <v-img :src="url==null? require('@/assets/icono_foto_credencial.png') : url"></v-img>
                    </v-avatar>
                  </v-row>
                </v-col>
                <v-col cols="8">
                  <v-row align="center" justify="center">
                    <v-file-input
                        accept="image/png, image/jpeg"
                        placeholder="Elija una imagen"
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

          <v-row justify="center" class="pt-6">
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
                >Crear credencial</span>
              </v-btn>
            </v-col>
          </v-row>
        </v-col>
      </v-container>
    </v-form>
  </v-sheet>
</template>

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
      v => (v && (v.length <= 20)) || 'Su nombre debe contener a lo más 30 caracteres.',
    ],
  }),

  methods: {
    validate () {
      if (this.$refs.form.validate() && this.name.length < 20){
        this.$router.push({name: 'CreateCredential', params: {name: this.name, url: this.url}})
      }
    },
    Preview_image() {
      if(this.image){

        this.url= URL.createObjectURL(this.image)
      }else{
        this.url = URL.createObjectURL(require('@/assets/icono_foto_credencial.png'))
      }
    }
  },
}
</script>

<style scoped>

</style>