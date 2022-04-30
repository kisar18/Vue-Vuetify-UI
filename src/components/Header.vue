<template>
  <v-card class="nav">
    <v-app-bar
      class="app-bar"
    >
      <v-app-bar-nav-icon class="nav-icon"></v-app-bar-nav-icon>
      <v-app-bar-title class="nav-text">Vuetify</v-app-bar-title>

      <v-spacer></v-spacer>

      <v-container class="search-box">
        <input placeholder="Search" class="nav-text search-input">
        <v-icon class="search-icon">mdi-magnify</v-icon>
      </v-container>

      <v-spacer></v-spacer>

      <v-container class="icon-box d-none d-md-flex d-xs-none">
        <v-btn icon class="nav-icon">
          <v-badge content="5" color="red">
            <v-icon>mdi-email</v-icon>
          </v-badge>
        </v-btn>

        <v-btn icon class="nav-icon">
          <v-badge content="11" color="red">
            <v-icon>mdi-bell</v-icon>
          </v-badge>
        </v-btn>

        <v-btn icon class="nav-icon">
          <v-icon>mdi-account-circle</v-icon>
        </v-btn>
      </v-container>

      <v-btn @click="$emit('showMobMenu')" icon class="nav-icon d-flex d-xs-flex d-md-none">
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>
    </v-app-bar>
  </v-card>
</template>

<script>

export default {
  emits: ["showMobMenu"],

  data: () => ({
    //
  }),
}
</script>

<style scoped>
  .nav {
    cursor: default;
  }

  .app-bar {
    background-color: #1976d2;
  }

  .nav-text {
    color: var(--main-light);
    padding: 0;
    margin: 0;
  }

  .nav-text::placeholder {
    color: gray !important;
  }

  .nav-icon {
    color: var(--main-light);
    background-color: var(--main-primary-base);
    margin-right: 7px;
    font-size: 20px;
  }

  .icon-box {
    display: flex;
    width: auto;
  }

  .search-box {
    display: flex;
    align-items: center;
    background-color: var(--main-light);
    border-radius: 5px;
    height: 85%;
    width: auto;
  }

  .search-icon {
    color: gray;
    margin-left: 7px;
  }

  .search-input {
    width: 235px;
  }

  @media (max-width: 960px) {
    .search-input {
      width: 100px;
    }
  }

</style>
