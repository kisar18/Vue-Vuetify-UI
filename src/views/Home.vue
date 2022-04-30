<template>
  <v-app>
    <Header @showMobMenu="showMobileMenu"></Header>
    <MobileMenu v-if="mobileMenuVisible"></MobileMenu>
    <Form @click="closeMobileMenu"></Form>
    <Footer @click="closeMobileMenu"></Footer>
  </v-app>
</template>

<script>
import Header from '../components/Header.vue';
import MobileMenu from '../components/MobileMenu.vue';
import Form from '../components/Form.vue';
import Footer from '../components/Footer.vue';

export default {
  name: 'App',
  components: {
    Header,
    MobileMenu,
    Form,
    Footer,
  },
  data: () => ({
    mobileMenuVisible: false
  }),
  methods: {
    showMobileMenu() {
      this.mobileMenuVisible = !this.mobileMenuVisible;
    },

    closeMobileMenu() {
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
