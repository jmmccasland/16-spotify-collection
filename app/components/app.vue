<template lang="html">
<div>
  <div class="section">
    <div class="container">
      <div class="page">
        <div class="panel">
          <input v-on:keydown.enter="search(value)" v-model="value" class="panel-heading" type="text" >
          <song-item v-for="item in tracks" v-bind:track="item"></song-item>
        </div>
      </div>
    </div>
  </div>
</div>


</template>

<script>
import SongItem from './song-item.vue';

export default {
  components: {
    SongItem,
  },

  data() {
    return {
      tracks: [

      ],
    };
  },

  created() {
    this.search('Foo Fighters');
  },

  methods: {
    search(value) {
      fetch(`https://api.spotify.com/v1/search?query=${value}&type=track&offset=0&limit=20`)
      .then(r => r.json())
      .then((curr) => {
        this.tracks = curr.tracks.items;
      });
    }
  },
};
</script>
