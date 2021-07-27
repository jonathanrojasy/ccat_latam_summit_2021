<template>
  <v-container fluid fill-height class="px-0">
    <v-row justify="center" align="center">
      <v-col
          :cols="$vuetify.breakpoint.xs ? 12 : 10"
          :class="$vuetify.breakpoint.xs ? 'py-10' : 'py-16'"
      >
        <v-row align="center" justify="center">
          <v-card
              rounded
              height="600"
              width="450"
              :class="$vuetify.breakpoint.xs ? 'pa-3' : 'pa-6'"
          >
            <v-sheet
                style="border-radius: 15px;"
                class="cred-form"
                height="550"
            >
              <v-col cols="12" class="fill-height">
                <v-row>
                  <v-sheet
                      color="transparent"
                      :height="$vuetify.breakpoint.xs ? 142 : 124"
                  >
                  </v-sheet>
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
.cred-form{
  background-image: url("../assets/credencial_base.png");
  background-size: cover;
}
</style>