<template>
<div>
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

</style>
