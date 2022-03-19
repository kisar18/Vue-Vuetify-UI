<template>
  <v-card class="mobile-menu">
    <v-list-item class="list-item">
      <v-btn block class="btn">
        <v-badge content="5" color="red" class="badge">
          <v-icon left>
            mdi-email
          </v-icon>
        </v-badge>
        Messages
      </v-btn>
    </v-list-item>

    <v-list-item class="list-item">
      <v-btn block class="btn">
        <v-badge content="11" color="red" class="badge">
          <v-icon left>
            mdi-bell
          </v-icon>
        </v-badge>
        Notifications
      </v-btn>
    </v-list-item>

    <v-list-item class="list-item">
      <v-btn block class="btn">
        <v-icon left>
          mdi-account-circle
        </v-icon>
        Profile
      </v-btn>
    </v-list-item>
  </v-card>
</template>

<script>

export default {
  data: () => ({
    
  })
}
</script>

<style scoped>

.mobile-menu {
  width: 25%;
  position: absolute;
  right: 0;
  margin-top: 65px;
  border-radius: 0;
  z-index: 1;
}

@media (max-width: 960px){
  .mobile-menu {
    width: 50%;
  }
}

.list-item {
  margin: 0;
  padding: 0;
  height: 100%;
}

.btn {
  border-radius: 0 !important;
  font-size: 1rem;
  height: 65px;
}

.badge {
  margin-right: 18px;
}

</style>