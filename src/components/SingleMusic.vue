<template>
    <div class="col-lg-2 col-md-4 col-6 single-music-container">
        <img :src="image" :alt="title">

        <h1>Titolo</h1>
        <p>paragrafo</p>
    </div>
</template>

<script>
export default {
    name :"SingleMusic",
    props : ["image", "title", "author", "year"]
}
</script>

<style lang="scss" scoped>
.single-music-container{
    background-color: #2c2c48;
}
</style>