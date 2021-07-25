<template>
  <v-app>
    <Header/>
    <v-main>
      <v-container fluid class="pa-0">
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
  background-color: darkblue;
}
</style>
