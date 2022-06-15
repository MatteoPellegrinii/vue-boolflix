<template>
<div>
    <h2>{{movieobject.title}} {{movieobject.name}} </h2>
    <h4>lingua: {{movieobject.original_language}} </h4>
    <h5>voto {{votechange()}} </h5>
    <img :src="`http://image.tmdb.org/t/p/w500/${movieobject.poster_path}`" :alt="name">
</div>
 
</template>

<script>
export default {
  data(){
    return{
      votonuovo: '',
    }
  },
  name: 'MoviesAPi',
      props: {
        name: String,
        src: String,
        movieobject: Object
    },
    methods:{
      votechange(){
        this.votonuovo = Math.floor(this.movieobject.vote_average / 2) ;
        return this.votonuovo
      }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
img{
  width: 300px;
}
</style>