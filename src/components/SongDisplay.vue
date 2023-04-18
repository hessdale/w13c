<template>
  <div>
    <section>
      <h1>Now playing:{{ current.title }}</h1>
    </section>
    <section>
      <h1>Playlist</h1>
      <button v-for="song in songs" :key="song[`id`]">
        {{ song[`title`] }} - {{ song[`artist`] }}
      </button>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      current: {},
      index: 0,
      songs: [
        {
          title: `song1`,
          artist: `artist1`,
        },
        {
          title: `song2`,
          artist: `artist2`,
        },
        {
          title: `song3`,
          artist: `artist3`,
        },
        {
          title: `song4`,
          artist: `artist4`,
        },
        {
          title: `song5`,
          artist: `artist5`,
        },
      ],
    };
  },
};
</script>

<style scoped>
</style>