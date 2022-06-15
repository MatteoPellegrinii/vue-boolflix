<template>
  <div id="app">
    <SearchProjectVue @search="searchmovie" />
    <MoviesProjectVue :msg="text"/>
  </div>
</template>

<script>
import MoviesProjectVue from './components/MoviesProject.vue';
import SearchProjectVue from './components/SearchProject.vue';


export default {
  name: 'App',
  components: {
    MoviesProjectVue,
    SearchProjectVue
},
data(){
  return{
    text: "",
  }
},
methods: {
          searchmovie(parameter){
            this.text = parameter
            console.log(this.text);
        }
}
}

</script>

<style lang="scss">

</style>
