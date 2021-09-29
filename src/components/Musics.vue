<template>
  <div class="container-fluid">
    <div class="row music-container">
      <SingleMusic :image="SingleMusic.poster" :title="SingleMusic.title" :author="SingleMusic.author" :year="SingleMusic.year" />
    </div>
    
  </div>

  
</template>

<script>
import SingleMusic from "../components/SingleMusic.vue";
import axios from "axios";
export default {
  name: 'Musics',

  components : {
    SingleMusic,
  },

  data : function (){
    return {
      dataMusics : [],
    }
  },

  mounted () {
      axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((response) => {

        // console.log(response.data.response);

        this.dataMusics = response.data.response

        console.log(this.dataMusics);
    })
  },

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

.container-fluid{
  background-color: black;
}

.row.music-container {
    padding: 50px 200px;
}
</style>
