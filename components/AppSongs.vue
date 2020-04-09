<template>
  <div class="songs-container">
    <app-song-card v-for="song in songs" :key="song.id" :song="song"/>
  </div>
</template>

<script>
import AppSongCard from '@/components/AppSongCard';

export default {
  props: ['songs'],
  components: {
    AppSongCard
  }
};
</script>

<style>
</style>