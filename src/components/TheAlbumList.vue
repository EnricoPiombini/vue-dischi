<template>
    <div>
        <main>
            <div class="container">

                <select v-model="genre" @change="genreChange(genre)">
                    <option disabled selected>Pick the genre</option>
                    <option v-for="(genre, i) in PickGenreList" :key="i"> {{ genre }}
                    </option>


                </select>

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
    name: "TheDiscs",
    components: { TheSingleDisc },
    data() {
        return {
            apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
            albumInfo: [],
            listGenre:[],
            genre:0,
        }
    },
    methods: {
        fetchMusicList() {
            axios.get(this.apiUrl).then((response) => {
                this.albumInfo.push(...response.data.response)
            });

        },
        genreChange(genre) {
            console.log(genre);
        }
    },

    mounted() {
        this.fetchMusicList()
    },

    computed: {
        PickGenreList() {
            const listGenre = [];
            this.albumInfo.forEach(element => {
                if (!listGenre.includes(element.genre)) {
                    listGenre.push(element.genre)
                }
            });
            return listGenre;
        }
    }
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