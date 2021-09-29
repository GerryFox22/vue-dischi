<template>
    <div  class="single-music-container p-4">
        <img class="img-fluid " :src="music.poster" :alt="title">

        <h1 class="text-center mb-4 mt-3">{{music.title}}</h1>
        <p class="text-center">{{music.author}}</p>
        <p class="text-center">{{music.year}}</p>

    </div>
</template>

<script>
export default {
    name :"SingleMusic",
    props : ["music"]
}
</script>

<style lang="scss" scoped>
.single-music-container{
    background-color: #2e3a46;
    height: 100%;
    h1 {
        color: white;
        font-size: 1.5rem;
    }
    p{
        color: gray;
        margin: 0;
    }
}
</style>