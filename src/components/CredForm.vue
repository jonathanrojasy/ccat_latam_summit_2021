<template>
  <v-sheet
      color="#ffA1B9"
      class="py-12"
  >
    <v-form
        ref="form"
        v-model="valid"
        lazy-validation
    >
      <v-container fluid fill-height>
        <v-col>
          <v-row justify="center">
            <span
                class="text-h6 font-weight-bold"
                style="color: #1A237E"
            >Ingresa tu Nombre y Apellido</span>
          </v-row>
          <v-row justify="center">
            <v-col :cols="$vuetify.breakpoint.xs ? 12 : 10">
              <v-text-field
                  v-model="name"
                  :counter="10"
                  :rules="nameRules"
                  solo
                  flat
                  style="border-radius: 8px"
                  required
              ></v-text-field>
            </v-col>
          </v-row>

          <v-row align="center" justify="center">
            <v-col :cols="$vuetify.breakpoint.xs ? 10 : 8">
              <v-row align="center" justify="center">
                <v-col cols="4">
                  <v-row align="center" justify="center">
                    <v-avatar
                        class="profile"
                        size="100"
                    >
                      <v-img :src="require('@/assets/foto_icon.png')"></v-img>
                    </v-avatar>
                  </v-row>
                </v-col>
                <v-col cols="8">
                  <v-row align="center" justify="center">
                    <v-btn
                        text
                        color="#FE718F"
                    >
                      <span
                          class="font-weight-bold"
                          :class="$vuetify.breakpoint.xs ? 'text-caption' : 'text-subtitle-1'"
                      >Sube una foto</span>
                    </v-btn>
                  </v-row>
                </v-col>
              </v-row>
            </v-col>
          </v-row>

          <v-row justify="center">
            <v-col :cols="$vuetify.breakpoint.xs ? 12 : 10">
              <v-btn
                  :disabled="!valid"
                  color="pink lighten-2"
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
    name: '',
    nameRules: [
      v => !!v || 'Ingrese su nombre por favor.',
      v => (v && (v.length >= 2)) || 'Su nombre debe contener por lo menos 2 caracteres.',
      v => (v && (v.length <= 30)) || 'Su nombre debe contener a lo más 30 caracteres.',
    ],
  }),

  methods: {
    validate () {
      this.$refs.form.validate()
    },
  },
}
</script>

<style scoped>

</style>