<template>
  <v-container fluid fill-height class="px-0">
    <v-row justify="center" align="center">
      <v-col
          :cols="$vuetify.breakpoint.xs ? 12 : 10"
          :class="$vuetify.breakpoint.xs ? 'py-10' : 'py-16'"
      >
        <v-row justify="center">
          <v-card
              rounded
              width="600"
              :class="$vuetify.breakpoint.xs ? 'pa-3' : 'pa-6'"
          >
            <v-sheet
                color="#20068D"
                style="border-radius: 15px;"
            >
              <v-col cols="12">
                <v-row>
                  <v-col cols="12">
                    <v-sheet
                        color="transparent"
                    >
                      <v-col

                          :class="$vuetify.breakpoint.xs ? 'pa-8' : 'pa-12'"
                      >
                        <v-row justify="start">
                        <span
                            class="font-weight-black white--text"
                            :class="$vuetify.breakpoint.xs ? 'text-h5' : 'text-h4'"
                        >TU CREDENCIAL<br>DMA TEAM</span>
                        </v-row>
                      </v-col>
                    </v-sheet>
                  </v-col>
                </v-row>
                <v-row align="center" justify="center">
                  <v-col cols="12" class="pa-0">
                    <CredForm/>
                  </v-col>
                </v-row>
              </v-col>
            </v-sheet>
          </v-card>
        </v-row>
      </v-col>
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