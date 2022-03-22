<template>
  <v-container class="results">
    <h1 class="title my-4">↓ Results ↓</h1>
    <v-container class="list">
      <v-list>
        <v-list-item>
          <v-list-item-header>
            <v-list-item-title class="list-item-text">First name: {{ this.$route.params.firstName }}</v-list-item-title>
          </v-list-item-header>
        </v-list-item>
        <v-divider></v-divider>
        <v-list-item>
          <v-list-item-header>
            <v-list-item-title class="list-item-text">Last name: {{ this.$route.params.lastName }}</v-list-item-title>
          </v-list-item-header>
        </v-list-item>
        <v-divider></v-divider>
        <v-list-item>
          <v-list-item-header>
            <v-list-item-title class="list-item-text">Email: {{ this.$route.params.email }}</v-list-item-title>
          </v-list-item-header>
        </v-list-item>
        <v-divider></v-divider>
        <v-list-item>
          <v-list-item-header>
            <v-list-item-title class="list-item-text">Gender: {{ this.$route.params.gender }}</v-list-item-title>
          </v-list-item-header>
        </v-list-item>
        <v-divider></v-divider>
        <v-list-item>
          <v-list-item-header>
            <v-list-item-title class="list-item-text">Mood: {{ this.$route.params.mood }}</v-list-item-title>
          </v-list-item-header>
        </v-list-item>
        <v-divider></v-divider>
        <v-list-item>
          <v-list-item-header>
            <v-list-item-title class="list-item-text">Employed: {{ this.$route.params.gender ? "Yes" : "No" }}</v-list-item-title>
          </v-list-item-header>
        </v-list-item>
        <v-divider></v-divider>
        <v-list-item>
          <v-list-item-header>
            <v-list-item-title class="list-item-text">Notes: {{ this.$route.params.notes }}</v-list-item-title>
          </v-list-item-header>
        </v-list-item>
      </v-list>
    </v-container>

    <router-link class="go-back my-4" :to="{ name: 'Home' }">
      <div class="text-h3">Go Back</div>
    </router-link>
  </v-container>
</template>

<script>
export default {
    data: () => ({
      //
    }),
}
</script>

<style scoped>
  .results {
    margin-top: 64px;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .title {
    color: #1976d2;
    font-weight: bold;
  }

  .list-item-text {
    font-size: 20px;
    font-weight: bold;
  }

  .list {
    border: 10px solid #1976d2;
    border-radius: 10px;
    width: 50%;
  }

  .go-back {
    color: #1976d2;
    text-decoration: none;
  }

  @media (max-width: 960px) {
    .list {
      width: 95%;
    }
    .list-item-text {
      font-size: 17px;
    }
  }

</style>