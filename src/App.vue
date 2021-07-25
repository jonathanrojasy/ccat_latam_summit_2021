<template>
  <v-app>
    <Header/>
    <v-main>
      <v-container fluid>
        <CredCard/>
      </v-container>
    </v-main>
    <Footer/>
  </v-app>
</template>

<script>
import Header from "@/components/Header";
import Footer from "@/components/Footer";
import CredCard from "@/components/CredCard";
export default {
  name: 'App',
  components: {
    Header,
    Footer,
    CredCard
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background-color: darkblue;
}
</style>
