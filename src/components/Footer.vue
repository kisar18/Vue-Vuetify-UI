<template>
  <v-card>
    <v-footer class="footer">
      <span>Contact us:</span>
      <v-btn
        v-for="button in buttons"
        :key="button"
        class="nav-icon"
        icon
        elevation="0"
        :href= button.link
      >
        <v-icon size="24px">
          {{ button.icon }}
        </v-icon>
      </v-btn>
    </v-footer>
  </v-card>
</template>

<script>

export default {
  data: () => ({
    buttons: [
      {icon: 'mdi-facebook', link:'https://www.facebook.com'},
      {icon: 'mdi-twitter', link: 'https://www.twitter.com'},
      {icon: 'mdi-instagram', link: 'https://www.instagram.com'}
    ]
  })
}
</script>

<style scoped>
  .footer {
    display: flex;
    justify-content: center;
    position: fixed;
    bottom: 0;
    left: 0;
    background-color: var(--main-primary-base);
    color: var(--main-light);
    width: 100%;
    height: 7%;
    cursor: default;
  }

  .nav-icon {
    color: var(--main-light);
    background-color: var(--main-primary-base);
    margin-right: 7px;
    font-size: 20px;
  }

</style>