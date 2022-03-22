<template>
  <v-app>
    <Header :mobileMenuVisible="mobileMenuVisible" @showmobmenu="mobileMenuVisible = !mobileMenuVisible"></Header>
    <FormResults @click="closemobilemenu"></FormResults>
    <Footer @click="closemobilemenu"></Footer>
  </v-app>
</template>

<script>
import Header from '../components/Header.vue'
import Footer from '../components/Footer.vue'
import FormResults from '../components/FormResults.vue'

export default {
  name: 'App',
  components: {
    Header,
    Footer,
    FormResults
  },
  data: () => ({
    mobileMenuVisible: false
  }),
  methods: {
    showmobilemenu(value) {
      this.mobileMenuVisible = value;
    },
    closemobilemenu() {
      if(this.mobileMenuVisible) {
        this.mobileMenuVisible = false;
      }
    }
  },
}
</script>

<style>
  html { 
    overflow-y: auto !important;
  }
</style>
