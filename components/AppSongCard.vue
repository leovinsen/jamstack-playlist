<template>
  <div class="song">
    <img height="100px" :src="song.album.cover_medium" alt="Album cover" class="song-image">
    <div class="song-details">
      <h1 class="song-title">{{song.title}}</h1>
      <div class="song-details--extra">
        <p class="song-artist"> {{song.artist.name}}</p>
        <p>·</p>
        <p class="song-length">{{ song.duration }} seconds</p>
      </div>
    </div>

    <div class="song-play-container">
      <a :href="song.link" class="song-player">
        <img width="25px" src="/play-solid.svg" alt="Song Play  Button" />
      </a>
    </div>
  </div>
</template>

<script>
export default {
  props: ["song"]
};
</script>

<style>
</style>