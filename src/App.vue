<template>
  <div id="app">
     <!-- Font awesome --> 
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css"/>
    
    <TopBar />
    <Musics />
  </div>
</template>

<script>
import Musics from './components/Musics.vue';
import TopBar from './components/TopBar.vue';
// import axios from "axios";

export default {
  name: 'App',
  components: {
    Musics,
    TopBar,
  }
}
</script>

<style lang="scss">

@import "style/general.scss";
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  
}
</style>
