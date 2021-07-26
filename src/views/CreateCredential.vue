<template>
  <v-container fluid fill-height>
    <v-row justify="center" align="center">
      <v-card
          class="flex"
          color="transparent"
          flat
          max-width="600"
      >
        <v-card-title class="justify-center">
          <ShowImage :name="nameSet" />
        </v-card-title>
      </v-card>
      <v-card
          color="transparent"
          flat
      >
        <v-card-title>
          <div>
            <v-col>
              <v-row justify="center" class="py-2">
                <v-btn
                    x-large
                    color="#fe718f"
                    class="subtitle-1 font-weight-bold white--text"
                    block
                    @click="downloadWithAxios(require('@/assets/Fondo-credencial.png'),'Fondo-credencial.png')"
                >DESCARGAR</v-btn>
              </v-row>
              <v-row justify="center" class="py-2">
                <v-btn
                    to="/"
                    x-large
                    block
                    outlined
                    color="#fe718f"
                    class="subtitle-1 font-weight-bold"
                >VOLVER</v-btn>
              </v-row>
            </v-col>
          </div>
        </v-card-title>
      </v-card>
    </v-row>
  </v-container>
</template>

<script>
import ShowImage from "@/components/ShowImage";
import axios from 'axios'
export default {
  name: 'CreateCredential',
  components:{
    ShowImage,
  },
  computed:{
    nameSet(){
      return this.$route.params.name
    }
  },
  methods:{
    forceFileDownload(response, title) {
      console.log(title)
      const url = window.URL.createObjectURL(new Blob([response.data]))
      const link = document.createElement('a')
      link.href = url
      link.setAttribute('download', title)
      document.body.appendChild(link)
      link.click()
    },
    downloadWithAxios(url, title) {
      axios({
        method: 'get',
        url,
        responseType: 'arraybuffer',
      })
          .then((response) => {
            this.forceFileDownload(response, title)
          })
          .catch(() => console.log('error occured'))
    },
  }
}
</script>
