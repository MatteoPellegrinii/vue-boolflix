<template>
<div class="contenitoreproject">
    <MoviesApiVue 
        v-for="(item, index) in this.arrayfilm"
        :key="index"
        :movieobject="item"
        :name =  "item.title"
        :src = "item.poster_path"
      />
    <SerieApi
        v-for="(item, index) in this.arrayserie"
        :key="index"
        :movieobject="item"
        :name =  "item.title"
        :src = "item.poster_path"
    />
    </div>
 
</template>

<script>


import MoviesApiVue from './MoviesApi.vue';
import SerieApi from './SerieApi.vue'
export default {
    name: "MoviesProject",
    components: { MoviesApiVue, SerieApi },
    props:{
        msg: String,
        arrayfilm: Array,
        arrayserie: Array,
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.contenitoreproject{
    width: 100%;
    background-color: grey;
    min-height: calc(100vh - 50px);
    display: flex;
    flex-wrap: wrap;
}
</style>
