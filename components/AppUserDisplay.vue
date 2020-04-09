<template>
  <div class="header-id-display">
    <img class="user-image" :src="user.picture" alt="" />
    <p class="user-name"> {{ user.name }}</p>
    <a @click="changeUserName" href class="switch-text">Switch accounts?</a>
  </div>
</template>

<script>
export default {
  props: ['user'],
  methods: {
    changeUserName() {
      let result = window.confirm("Are you sure you want to do this?")
      if(result) this.$store.dispatch("user/removeUser")
      this.$store.commit("songs/SET_SONGS", []);
    }
  }
};
</script>

<style>
</style>