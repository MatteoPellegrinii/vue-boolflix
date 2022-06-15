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
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
