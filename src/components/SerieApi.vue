<template>
<div>
    <h2>{{movieobject.name}} </h2>
    <h4>lingua: <lang-flag :iso="movieobject.original_language" />  </h4>
    <h5>voto  
      <font-awesome-icon class="star-icon" icon="fa-solid fa-star" v-for="(star, index) in votechange"
                    :key="index" /> 
      <font-awesome-icon class="star-icon" icon="fa-regular fa-star" v-for="(star, index) in starempty"
                    :key="index" /> 
    </h5>
    <img :src="`http://image.tmdb.org/t/p/w500/${movieobject.poster_path}`" :alt="name">
</div>
 
</template>

<script>
export default {
  name: 'SerieApi',
      props: {
        name: String,
        src: String,
        movieobject: Object
    },
    computed:{
      votechange(){
        return Math.floor(this.movieobject.vote_average / 2) ;
      },
      starempty(){
        return 5 -  Math.floor(this.movieobject.vote_average / 2) ;
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