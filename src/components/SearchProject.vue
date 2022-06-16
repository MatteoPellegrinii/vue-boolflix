<template>
<div class="contenitoresearch">
    <div class="logo">BOOLFLIX</div>
    <div class="input">
        <input type="search" placeholder="searchbar" v-model="inputText" @keyup.enter="$emit('search', inputText)" >
    </div>
        
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

<style scoped lang="scss">
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.contenitoresearch{
    width: 100%;
    height: 50px;
    background-color: black;
    display: flex;
    .logo{
        width: 50%;
        height: 100%;
        color: red;
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: 30px;
    }
    .input{
        width: 50%;
        padding-right: 15%;
        height: 100%;
        display: flex;
        align-items: center;
        justify-content: flex-end;
        input{
            width: 200px;
            height: 25px;
        }
    }
}
</style>