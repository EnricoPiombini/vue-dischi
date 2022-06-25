<template>
    <div>
        <main>
            <div class="container">


                <div class="row row-cols-5">
                    <div class="col" v-for="disc in albumInfo" :key="disc.author">
                        <TheSingleDisc :author-name="disc">

                        </TheSingleDisc>
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
        }
    },
    methods: {
        fetchMusicList() {
            axios.get(this.apiUrl).then((response) => {
                this.albumInfo.push(...response.data.response)



            });

        },
    },
    mounted() {
        this.fetchMusicList()
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