<template>
    <div class="d-flex">
        <div class="input-group">
            <select type="text" class="form-select">
                <option value="">Pick a genre</option>
                <option v-for="(genere, i) in PickGenreList" :key="i" :value="genere"> {{ genere }} </option>
            </select>
            <button class="btn btn-outline-light" @click="onClick" >Search</button>
        </div>
    </div>

</template>

<script>
export default {
    props: {
    PickGenreList: Array,
    },

    data() {
        return {
        genre:""
        }
    },

    methods:{
        onClick(){
            this.$emit("searchGenre", this.genre)
        }
    }
};


</script>

<style lang="scss" scoped>
</style> 