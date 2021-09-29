<template>
  <div class="container-fluid">
    <div class="row music-container">
      <div v-for="(music,index) in dataMusics" :key="index" class="col-lg-3 col-md-4 col-6 mb-4 ">
        <SingleMusic :music="music" />
      </div>
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

        this.dataMusics = response.data.response.slice()

        console.log(this.dataMusics);
    })
  },

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

.container-fluid{
  background-color: #1e2d3b
;
}

.row.music-container {
    width: 70%;
    margin: 0 auto;
    padding-top: 20px;
}
</style>
