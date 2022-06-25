<template>
    <div class="content text-center">

        <img :src="authorName.poster" alt="" class="w-100">
        <h5 class="text-white fw-bold text-uppercase"> {{ authorName.title }} </h5>
        <p>{{ authorName.author }} </p>
        <p>{{ authorName.year }}</p>
    </div>

</template>

<script>
export default {
    props: {
        authorName: Object,
    },
    name: "TheDisc",

}

</script>


<style lang="scss" scoped>
.content {
    background-color: #37374B;
}
</style>