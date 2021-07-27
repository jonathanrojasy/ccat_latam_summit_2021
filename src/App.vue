<template>
  <v-app>
    <Header/>
    <v-main>
      <v-container fluid>
        <router-view></router-view>
      </v-container>
    </v-main>
    <Footer/>
  </v-app>
</template>

<script>
import Header from "@/components/Header";
import Footer from "@/components/Footer";
export default {
  name: 'App',
  components: {
    Header,
    Footer,
  }
}
</script>

<style>
#app {
  background-image: url("../src/assets/fondo_pag.png");
  background-attachment: fixed;
  background-position: top;
  background-size: cover;
}
</style>