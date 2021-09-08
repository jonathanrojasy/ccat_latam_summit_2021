<template>
  <v-container fluid fill-height class="px-0">
    <v-row justify="center" align="center">
      <v-col
          :cols="$vuetify.breakpoint.xs ? 12 : 11"
          :class="$vuetify.breakpoint.xs ? 'pb-10' : 'pb-16'"
      >
        <v-row align="center" justify="center">
          <v-card
              rounded
              max-height="700"
              max-width="420"
              :class="$vuetify.breakpoint.xs ? 'px-3' : 'px-3'"
          >
            <v-sheet
                style="border-radius: 15px;"
                class="cred-form"
                height="650"
            >
              <v-col cols="12" class="fill-height">
                <v-row>
                  <v-sheet
                      color="transparent"
                      :height="$vuetify.breakpoint.xs ? 115 : 138"
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
  background-size: contain;
  background-position: center;
}
</style>