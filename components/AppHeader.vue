<template>
  <header class="site-header">
    <div v-if="!loaded" class="loader"></div>
    <div v-if="dataLoaded && loaded" class="site-header-container">
      <h1 class="site-title">Your Favorite Deezer Tracks</h1>
      <app-user-search v-if="!user"/>
      <app-user-display :user="user" v-else/>
    </div>
  </header>
</template>

<script>
import AppUserDisplay from "@/components/AppUserDisplay"
import AppUserSearch from "@/components/AppUserSearch"
export default {
  components: {
    AppUserDisplay,
    AppUserSearch
  },
  computed: {
    user() {
      return this.$store.state.user.data;
    },
    dataLoaded() {
      return this.$store.state.dataLoaded;
    },
    loaded() {
      return this.$store.state.searchLoaded;
    }
  }
};
</script>

<style>
</style>