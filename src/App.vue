<template>
  <div id="app">
    <SearchProjectVue @search="searchmovie" />
    <MoviesProjectVue :msg="text" :arrayfilm="newArray" :arrayserie="newArrayserie" />
    
  </div>
</template>

<script>
import MoviesProjectVue from './components/MoviesProject.vue';
import SearchProjectVue from './components/SearchProject.vue';
import axios from 'axios';


export default {
  name: 'App',
  components: {
    MoviesProjectVue,
    SearchProjectVue
},
data(){
  return{
    text: "",
    newapiUrl:'',
    newArray: [],
    apiserie: '',
    newArrayserie: []
  }
},
methods: {
          searchmovie(parameter){
            this.text = parameter
            this.newapiUrl = 'https://api.themoviedb.org/3/search/movie?api_key=782c0bd692401e174879999a38995534&language=' + 'it-It' + '&query=' + parameter  + '&page=1&include_adult=false';
            this.apiserie = 'https://api.themoviedb.org/3/search/tv?api_key=782c0bd692401e174879999a38995534&language=en-US&page=1&query=' + parameter + '&include_adult=false',
            this.getMovie()
            this.getSerie()
        },
        getMovie(){
            axios.get(this.newapiUrl)
            .then(result =>{
            this.newArray = result.data.results;
            console.log(result);
        })
          },
        getSerie(){
            axios.get(this.apiserie)
            .then(result =>{
            this.newArrayserie = result.data.results;
            console.log(result);
            console.log(this.newArrayserie);

          })
        }
}
}

</script>

<style scoped lang="scss">
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
