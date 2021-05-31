<template>
  <div>
    <v-app-bar color="primary">
      <v-btn :to="{ name: 'welcome' }" class="mr-8">
        Welcome
      </v-btn>
      <v-btn :to="{ name: 'calendar' }" class="mr-8">
        Calendar
      </v-btn>

      <v-spacer></v-spacer>

      <v-btn v-if="!isLogged" :to="{ name: 'login' }" class="mr-2">
        Login
      </v-btn>
      <v-btn v-if="isLogged" @click="logout">
        Logout
      </v-btn>
    </v-app-bar>
  </div>
</template>

<script>
import { mapGetters } from 'vuex'

export default {
  name: "AppHeader.vue",
  data() {
    return {
    }
  },
  computed: {
    ...mapGetters(['isLogged'])
  },
  methods: {
    logout() {
      this.$store.dispatch('logout')
    }
  }
}
</script>

<style scoped>
</style>


CREATE DATABASE laravel_planner DEFAULT CHARACTER SET utf8 COLLATE utf8_unicode_ci;

GRANT ALL ON laravel_planner.* TO 'laravel_user'@'localhost' IDENTIFIED BY '197346825aveda';
