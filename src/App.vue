<template>
  <v-app>
    <Header :mobileMenuVisible="mobileMenuVisible" @showmobmenu="mobileMenuVisible = !mobileMenuVisible"></Header>
    <Form @click="closemobilemenu"></Form>
    <Footer @click="closemobilemenu"></Footer>
  </v-app>
</template>

<script>
import Header from './components/Header.vue'
import Form from './components/Form.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'App',

  components: {
    Header,
    Form,
    Footer
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
