<template>
<div>
    <h2>{{movieobject.title}} {{movieobject.name}} </h2>
    <img :src="`http://image.tmdb.org/t/p/w500/${movieobject.poster_path}`" :alt="name">
</div>
 
</template>

<script>
export default {
  name: 'MoviesAPi',
      props: {
        name: String,
        src: String,
        movieobject: Object
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
img{
  width: 300px;
}
</style>