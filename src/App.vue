<template>
  <Header></Header>
</template>

<script>
import Header from './components/Header'

export default {
  name: 'App',

  components: {
    Header
  },

  data: () => ({
    //
  }),
}
</script>

<style>
  html { 
    overflow-y: auto !important;
  }
</style>
