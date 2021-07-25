<template>
  <v-card
      color="pink lighten-3"
      flat
      class="py-14 px-16"
  >
    <v-col>
      <v-form
          ref="form"
          v-model="valid"
          lazy-validation
      >
        <span
            class="text-h6 font-weight-bold"
            style="color: #1A237E"
        >Ingresa tu Nombre y Apellido</span>
        <v-text-field
            class="pt-3"
            v-model="name"
            :counter="10"
            :rules="nameRules"
            solo
            flat
            style="border-radius: 8px"
            required
        ></v-text-field>

        <v-row align="center" class="px-12 pb-6">
          <v-col cols="4">
            <v-avatar
                class="profile"
                color="pink lighten-2"
                size="95"
                style="border-style: solid; border-width: 3px;"
            >
              <v-img src="https://cdn.vuetifyjs.com/images/profiles/marcus.jpg"></v-img>
            </v-avatar>
          </v-col>
          <v-col cols="8">
            <v-btn
                text
                color="indigo darken-4"
            >
              <span class="text-subtitle-1 font-weight-bold">Sube una foto</span>
            </v-btn>
          </v-col>
        </v-row>

        <v-btn
            :disabled="!valid"
            color="pink lighten-2"
            class="mr-4 white--text font-weight-bold text-h6"
            @click="validate"
            depressed
            x-large
            block
        >
          Crear credencial
        </v-btn>
      </v-form>
    </v-col>
  </v-card>
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