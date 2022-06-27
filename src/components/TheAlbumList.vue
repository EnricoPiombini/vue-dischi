<template>
  <div>
    <main>
      <div class="container">


        <div class="row row-cols-5">
          <div class="col" v-for="disc in albumInfo" :key="disc.author">
            <TheSingleDisc :info="disc"></TheSingleDisc>
          </div>

        </div>
      </div>
    </main>
  </div>




</template>


<script>
import axios from "axios";
import TheSingleDisc from "./TheSingleDisc.vue";
export default {
  props:{
searchGenre:String,
  },
  name: "TheAlbums",
  components: { TheSingleDisc },
  data() {
    return {
      apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
      albumInfo: [],
      
    }
  },
  methods: {
    fetchMusicList() {
      axios.get(this.apiUrl).then((response) => {
        this.albumInfo = response.data.response

        this.$emit("genresUpdated", this.PickGenreList())
      });


      // genreChange(genre) {
      //   console.log(genre);
      // },
    },
    PickGenreList() {
      const listGenre = [];
      this.albumInfo.forEach(album => {
        if (!listGenre.includes(album.genre)) {
          listGenre.push(album.genre)
        }
      });
      return listGenre;
    }



  },
  mounted() {
    this.fetchMusicList()
  },

}

</script>

<style lang="scss" scoped>
main {
  background-color: #1E2D3B;

  .container {
    padding-top: 3rem;
    padding-left: 5rem;
    padding-right: 5rem;
  }
}
</style>