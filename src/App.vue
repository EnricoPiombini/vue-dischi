<template>
  <div>
    <TheHeader :PickGenreList="PickGenreList" @searchGenre="onSearchGenre"></TheHeader>
    <TheAlbumList @genresUpdated="onGenresUpdated" @searchGenre="onSearchGenre"></TheAlbumList>
  </div>
</template>

<script>
import TheAlbumList from './components/TheAlbumList.vue'
import TheHeader from './components/TheHeader.vue'

export default {
  name: 'App',
  components: {
    TheAlbumList,
    TheHeader
  },
  props: {

  },


  data() {
    return {
      PickGenreList: [],
      searchGenre: ""
    }

  },
  methods: {
    onGenresUpdated(PickGenreList) {
      console.log(PickGenreList);
      this.PickGenreList = PickGenreList

    },
    onSearchGenre(genre) {
      this.searchGenre = genre
    }
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
  height: 100vh;
}
</style>