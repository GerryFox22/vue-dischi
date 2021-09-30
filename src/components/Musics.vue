<template>
  <div class="container-fluid">
    <div class="select-container d-flex justify-content-center p-3">
      <SelectGenre @search="cercaFiltro"/>
      <SelectArtist  @search="cercaFiltro" />
    </div>
    <div class="row music-container row-cols-lg-5 ">
      <div v-for="(music,index) in filteredDataMusics" :key="index" class="col-md-4 col-sm-6 col-12 mb-4">
        <SingleMusic :music="music" />
      </div>
    </div>
  </div>

  
</template>

<script>
import SingleMusic from "../components/SingleMusic.vue";
import SelectGenre from "../components/SelectGenre.vue";
import SelectArtist from "../components/SelectArtist.vue";
import axios from "axios";
export default {
  name: 'Musics',

  components : {
    SingleMusic,
    SelectGenre,
    SelectArtist,
  },

  data : function (){
    return {
      dataMusics : [],
      filtroSelezionato :"",
    }
  },

  methods : {
    cercaFiltro : function(filtro){
      this.filtroSelezionato = filtro;
      console.log(this.filtroSelezionato)
    }
  },

  computed : {
    filteredDataMusics (){
      let newDataMusics = this.dataMusics.filter (
        (element) => {
          if (element.genre.includes(this.filtroSelezionato)){
            return element.genre.includes(this.filtroSelezionato);
          } else 
             return element.author.includes(this.filtroSelezionato);
        }
      )
      return newDataMusics;
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
