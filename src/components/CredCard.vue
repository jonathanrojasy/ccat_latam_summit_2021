<template>
  <v-container fluid fill-height class="py-6">
    <v-row justify="center" align="center">
      <v-sheet
          rounded
          class="pa-6"
          max-width="600"
      >
        <v-sheet
            color="indigo darken-4"
            style="border-radius: 15px;"
        >
          <v-card
              color="indigo darken-4"
              flat
              class="pa-12"
              style="border-radius: 15px;"
          >
            <v-col>
              <v-row>
              <span
                  class="text-h4 font-weight-black white--text"
              >TU CREDENCIAL</span>
              </v-row>
              <v-row>
              <span
                  class="text-h4 font-weight-bold white--text"
              >DMA TEAM</span>
              </v-row>
            </v-col>
          </v-card>
          <CredForm/>
        </v-sheet>
      </v-sheet>
    </v-row>
  </v-container>
</template>

<script>
import CredForm from "@/components/CredForm";
export default {
  name: "CredCard",
  components:{
    CredForm,
  }
}
</script>

<style scoped>

</style>