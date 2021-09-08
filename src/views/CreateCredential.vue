<template>
  <v-container fluid fill-height>
    <v-row justify="center" align="center">
      <v-card
          class="flex"
          color="transparent"
          flat
          max-width="600"
      >
        <v-card-title class="justify-center px-0">
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
                    color="#D85551"
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
                    color="#BFD8EB"
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
import html2canvas from 'html2canvas'
export default {
  name: 'CreateCredential',
  components:{
    ShowImage,
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
        windowHeight: document.documentElement.offsetHeight,
      }
      html2canvas(elem,opts).then(canvas => {
        const link = document.createElement("a");
        link.setAttribute("download", "culture-spring-ccat_credencial.png");
        link.setAttribute(
            "href",
            canvas.toDataURL("image/png").replace("image/png", "image/octet-stream")
        );
        link.click();
      });
    },
  }
}
</script>
