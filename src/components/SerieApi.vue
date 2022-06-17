<template>
<div class="contenitoreserie">

    <div class="card">
      <img class="none" :src="`http://image.tmdb.org/t/p/w200/${movieobject.poster_path}`" :alt="name">

      <div class="description d-flex flex-column">
          <h2>{{movieobject.name}} </h2>
          <h4>lingua: <lang-flag :iso="movieobject.original_language" />  </h4>
          <h5>voto  
            <font-awesome-icon class="star-icon" icon="fa-solid fa-star" v-for="(star, index) in votechange"
                    :key="index + 'stargood'" /> 
            <font-awesome-icon class="star-icon" icon="fa-regular fa-star" v-for="(star, index) in starempty"
                    :key="index + 'starbad'" /> 
          </h5>
          <p class="testo">{{movieobject.overview | truncate(500) }} </p>
      </div>



    </div>


    
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
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.contenitoreserie{
  margin: 20px;
  width: 200px;
  height: 300px;
  background-color: black;
      &:hover{
      .none{
        display: none;
      }
      .description{
        display: block;
      }
    }
  img{
    width: 200px;
    height: 300px;

  }
}
.card{
  position: relative;
}
.description{
  position: absolute;
  top: 0;
  left: 0;
  color: white;
  display: none;
}
.testo{
  font-size: 70%;
}
</style>