<template>
  <div id="app">
    <SpotifyHeader/>
    <SpotifyMain/>
  </div>
</template>

<script>
import SpotifyHeader from './components/SpotifyHeader.vue';
import SpotifyMain from './components/SpotifyMain.vue';

export default {
  name: 'App',
  components: {
    SpotifyHeader,
    SpotifyMain,
  }
}
</script>

<style lang="scss">
  @import "~bootstrap/scss/bootstrap.scss";
  
</style>
