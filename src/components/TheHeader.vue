<template>
    <div>
        <header>
            <div class="content d-flex justify-content-between align-items-center">
                <div class="logo">
                    <img src="../assets/logo.png" alt="" class="w-100">
                </div>
                <TheSearchBar :PickGenreList ="PickGenreList" @searchGenre="$emit('searchGenre, $event')"></TheSearchBar>
            </div>
        </header>

    </div>


</template>

<script>
import TheSearchBar from "./TheSearchBar.vue";

export default {
    components: { TheSearchBar },
    props: {
        PickGenreList : Array,
     },

    data(){
        return{
            
        }
    }
};




</script>


<style lang="scss" scoped>
header {
    background-color: #37374B;

    .logo {
        height: 40px;
        width: 40px;

    }
}
</style>