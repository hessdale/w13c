<template>
  <div>
    <section>
      <!-- using the variable is playing with an if statement to display the current playing song or ask user to play a song -->
      <div v-if="isPlaying != false">
        <h1>Now playing: {{ current.title }} by {{ current.artist }}</h1>
        <!-- using bind to get src from js current variable -->
        <img :src="current.image_url" alt="album art" height="250px" />
      </div>
      <!-- else it displays html -->
      <h1 v-else>Please play a song</h1>
    </section>
    <section>
      <h1>Playlist</h1>
      <!-- using a loop to add the buttons in to play a song -->
      <div v-for="song in songs" :key="song[`id`]">
        <!-- event listener to each of the buttons -->
        <button @click="play(song)">
          {{ song[`title`] }} - {{ song[`artist`] }}
        </button>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      //empty current variable for song data to be stored in
      current: {},
      //setting isPlaying variable to false on default
      isPlaying: false,
      //array of objects that hold all of the songs data (random generated words) and random pics
      songs: [
        {
          title: `rare`,
          artist: `new spell`,
          song_id: 32196,
          image_url: `https://images.pexels.com/photos/14844814/pexels-photo-14844814.jpeg?auto=compress&cs=tinysrgb&w=1600&lazy=load`,
        },
        {
          title: `expand`,
          artist: `energy patrol`,
          song_id: 35436,
          image_url: `https://images.pexels.com/photos/10815995/pexels-photo-10815995.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1`,
        },
        {
          title: `break`,
          artist: `funeral`,
          song_id: 31966,
          image_url: `https://images.pexels.com/photos/14691039/pexels-photo-14691039.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1`,
        },
        {
          title: `foster mayor`,
          artist: `cheap alchohol`,
          song_id: 36346,
          image_url: `https://images.pexels.com/photos/15331169/pexels-photo-15331169.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1`,
        },
        {
          title: `tooth`,
          artist: `jet`,
          song_id: 32356,
          image_url: `https://images.pexels.com/photos/14711412/pexels-photo-14711412.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1`,
        },
      ],
    };
  },
  //methods for defining function when user clicks button to play
  methods: {
    play(song) {
      //sets current to song info and sets is playing to true
      this.current = song;
      this.isPlaying = true;
    },
  },
};
</script>

<style scoped>
</style>