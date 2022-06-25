<template>
    <div>
        <div class="card">
            <div class="card-body">
                <img :src="authorName.poster" alt="" class="w-100">
                <h5> {{ authorName.title }} </h5>
                <p>{{ authorName.author }} {{ authorName.year }}  </p>
                
            </div>
        </div>

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


<style>
</style>