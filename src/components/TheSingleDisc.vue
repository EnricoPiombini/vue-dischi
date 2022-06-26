<template>
    <div class="content text-center">

        <img :src="info.poster" alt="" class="w-100">
        <h5 class="text-white fw-bold text-uppercase"> {{ info.title }} </h5>
        <p>{{ info.author }} </p>
        <p>{{ info.year }}</p>
    </div>

</template>

<script>
export default {
    props: {
        info: Object,
    },
    name: "TheDisc",

}

</script>


<style lang="scss" scoped>
.content {
    background-color: #37374B;
}
</style>