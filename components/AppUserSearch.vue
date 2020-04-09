<template>
  <div class="header-id-search">
    <div v-if="loaded">
      <input 
        v-model="userID" 
        placeholder="Enter your Deezer ID" 
        type="text" 
        class="header-input" 
        />
      <button @click="updateUserInfo">Search</button>
      <a href="#">
        <p class="header-small-text">How to find it</p>
      </a>
    </div>
  </div>
</template>

<script>
export default {
  data: () => ({
    userID: ''
  }),
  computed: {
    loaded() {
      return this.$store.state.searchLoaded
    }
  },
  methods: {
    async updateUserInfo() {
      this.$store.commit('SET_SEARCH_LOADED', false);
      if(this.userID !== "" ) {
        await this.$store.dispatch('user/setUser', this.userID)
        await this.$store.dispatch('songs/searchUserSongs', this.userID)
      }
      this.$store.commit("SET_SEARCH_LOADED", true);
    }
  }
};
</script>

<style>
</style>