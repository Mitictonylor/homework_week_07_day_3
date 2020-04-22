<template lang="html">
  <div>
<header-item></header-item>
<r-m-list :characters="characters"></r-m-list>
</div>
</template>

<script>
import Header from "./components/Header.vue"
import RMList from "./components/RMList.vue"
export default {
  name: "app",
  data() {
    return {
      characters: []
    }},

components:{
            "header-item": Header,
            "r-m-list": RMList,

},

methods:{

},
mounted(){
  fetch('https://rickandmortyapi.com/api/character/')
  .then(result => result.json()).then(characters => this.characters = characters.results)

}
}
</script>

<style lang="css" scoped>
*{
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body{
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
.btn{
  display: inline-block;
  border: none;
  background: #555;
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}
.btn:hover{
  background: #666
}

form{
  display: flex
}
input[type="text"]{
  flex: 40;
  padding: 5px
}
input[type='submit']{
  flex: 8
}
select{
  flex:10
}
</style>
