<template>
<div>
    <MoviesApiVue 
        v-for="(item, index) in this.array"
        :key="index"
        :movieobject="item"
        :name =  "item.title"
        :src = "item.poster_path"
      />
</div>
 
</template>

<script>
import MoviesApiVue from './MoviesApi.vue';
export default {
    name: "MoviesProject",
    components: { MoviesApiVue },
    props:{
        msg: String,
        array: Array,
    },
    data(){
        return {
            castMovie: [],
            apiUrl: 'https://api.themoviedb.org/3/search/movie?api_key=782c0bd692401e174879999a38995534&language=' + 'it-It' + '&query=' + 'star wars'  + '&page=1&include_adult=false'
        } 
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
