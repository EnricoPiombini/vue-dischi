<template>
  <div id="app">
    <TheAlbumList></TheAlbumList>
  </div>
</template>

<script>
import TheAlbumList from './components/TheAlbumList.vue'

export default {
  name: 'App',
  components: {
   TheAlbumList
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
