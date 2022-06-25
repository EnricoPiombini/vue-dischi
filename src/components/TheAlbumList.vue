<template>
    <div class="container">


        <div class="row">
            <div class="col-3" v-for="disc in albumInfo" :key="disc.author">
                <TheSingleDisc :author-name="disc">

                </TheSingleDisc>
            </div>
        </div>
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
</style>