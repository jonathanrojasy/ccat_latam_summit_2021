<template>
  <v-container fluid fill-height>
    <v-row justify="center" align="center">
      <v-card
          class="flex"
          color="transparent"
          flat
          max-width="600"
      >
        <v-card-title class="justify-center pa-0">
          <span class="white--text text-h6">¡Tu credencial para tus historias!</span>
          <ShowImage :name="nameSet" :url="imgSet"/>
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
                    color="teal darken-4"
                    class="subtitle-1 font-weight-bold white--text"
                    block
                    @click="captureDivHistorias()"
                >DESCARGAR</v-btn>
              </v-row>
              <v-row justify="center" class="py-2">
                <v-btn
                    to="/"
                    x-large
                    block
                    outlined
                    color="teal darken-4"
                    class="subtitle-1 font-weight-bold"
                >VOLVER</v-btn>
              </v-row>
            </v-col>
          </div>
        </v-card-title>
      </v-card>
      <img :src="output">
    </v-row>

    <v-row justify="center" align="center">
      <v-card
          class="flex"
          color="transparent"
          flat
          max-width="600"
      >
        <v-card-title class="justify-center pa-0">
          <span class="white--text text-h6 text-center text-break">¡Tu credencial para compartir en LinkedIn!</span>
          <ShowImage_LinkedIn :name="nameSet" :url="imgSet"/>
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
                    color="teal darken-4"
                    class="subtitle-1 font-weight-bold white--text"
                    block
                    @click="captureDivLinkedIn()"
                >DESCARGAR</v-btn>
              </v-row>
              <v-row justify="center" class="py-2">
                <v-btn
                    to="/"
                    x-large
                    block
                    outlined
                    color="teal darken-4"
                    class="subtitle-1 font-weight-bold"
                >VOLVER</v-btn>
              </v-row>
            </v-col>
          </div>
        </v-card-title>
      </v-card>
      <img :src="output">
    </v-row>
  </v-container>
</template>

<script>
import ShowImage from "@/components/ShowImage";
import ShowImage_LinkedIn from "../components/ShowImage_LinkedIn";
import html2canvas from 'html2canvas'
export default {
  name: 'CreateCredential',
  components:{
    ShowImage,
    ShowImage_LinkedIn,
  },
  data() {
    return {
      output: null
    }
  },
  computed:{
    nameSet(){
      return this.$route.params.name
    },
    imgSet(){
      return (this.$route.params.url)
    }
  },
  methods: {
    captureDivHistorias(){
      let elem = document.querySelector("#credhistorias")
      let opts = {
        scrollX: -window.scrollX,
        scrollY: -window.scrollY,
        windowWidth: document.documentElement.offsetWidth,
        windowHeight: document.documentElement.offsetHeight
      }
      html2canvas(elem,opts).then(canvas => {
        const link = document.createElement("a");
        link.setAttribute("download", "ccat_latam_summit_historias.jpg");
        link.setAttribute(
            "href",
            canvas.toDataURL("image/jpg").replace("image/jpg", "image/octet-stream")
        );
        link.click();
      });
    },
    captureDivLinkedIn(){
      let elem = document.querySelector("#credlinkedin")
      let opts = {
        scrollX: -window.scrollX,
        scrollY: -window.scrollY,
        windowWidth: document.documentElement.offsetWidth,
        windowHeight: document.documentElement.offsetHeight
      }
      html2canvas(elem,opts).then(canvas => {
        const link = document.createElement("a");
        link.setAttribute("download", "ccat_latam_summit_linkedin.jpg");
        link.setAttribute(
            "href",
            canvas.toDataURL("image/jpg").replace("image/jpg", "image/octet-stream")
        );
        link.click();
      });
    },
  }
}
</script>
