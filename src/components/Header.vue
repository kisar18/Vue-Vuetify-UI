<template>
  <v-app>
    <v-app-bar
      color="#1976d2"
    >
      <v-app-bar-nav-icon class="nav-icon"></v-app-bar-nav-icon>
      <v-app-bar-title class="nav-text">Vuetify</v-app-bar-title>

      <v-spacer></v-spacer>

      <v-container class="search-box">
        <v-icon class="search-icon">mdi-magnify</v-icon>
        <input placeholder="   Search..." class="nav-text search-input">
      </v-container>

      <v-spacer></v-spacer>

      <v-container class="icon-box d-none d-md-flex d-xs-none">
        <v-btn icon class="nav-icon">
          <v-badge content="4" color="red">
            <v-icon>mdi-email</v-icon>
          </v-badge>
        </v-btn>

        <v-btn icon class="nav-icon">
          <v-badge content="17" color="red">
            <v-icon>mdi-bell</v-icon>
          </v-badge>
        </v-btn>

        <v-btn icon class="nav-icon">
          <v-icon>mdi-account-circle</v-icon>
        </v-btn>
      </v-container>

      <v-btn icon class="nav-icon d-flex d-xs-flex d-md-none">
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>

    </v-app-bar>
  </v-app>
</template>

<script>

export default {
  data: () => ({
    //
  }),
}
</script>

<style scoped>

.nav-text {
  color: white;
  padding: 0;
  margin: 0;
}

.nav-text::placeholder {
  color: rgba(255, 255, 255, 0.35) !important;
}

.nav-icon {
  color: white;
  background-color: #1976d2;
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
  background-color: rgba(255, 255, 255, 0.15);
  border-radius: 5px;
  height: 85%;
  flex-shrink: 0;
  width: auto;
}

.search-box:hover {
  background-color: rgba(255, 255, 255, 0.25);
}

.search-icon {
  color: white;
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
