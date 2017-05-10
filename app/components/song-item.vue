<template lang="html">
  <div class="panel-block">
    <div class="media is-fullwidth">
      <figure class="media-left">
        <p class="image is-64x64">
          <img v-bind:src="track.album.images[0].url" alt="">
        </p>
      </figure>

      <div class="media-content">
        <h2 class="track__artist">{{track.artists[0].name}}</h2>
        <h3 class="track__name">{{track.name}}</h3>
      </div>
      <div class="media-right">
        <a target="_blank" v-bind:href="track.external_urls.spotify"><span class="fa fa-3x fa-spotify"></span></a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['track'],

  data() {
    return {
    };
  },

  methods: {

  },
};
</script>
