<template>
<div>
        <input type="search" placeholder="searchbar" v-model="inputText" @keyup.enter="$emit('search', inputText)" >
        <input type="button" value="submit">
</div>
</template>

<script>
export default{
    name: 'SearchProject',
    data(){
        return{
            inputText: "",
        }
    }
}
</script>

<style>
</style>