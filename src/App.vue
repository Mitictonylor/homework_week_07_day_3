<template lang="html">
  <div>
<header-item></header-item>
<div >
  <label for="character_select">Select a Character:</label>
  <select id="character_select" v-model="selectedCharacter">
    <option disabled value="">Select a Character</option>
    <option v-for="character in characters" :value="character">{{character.name}}</option>
  </select>

</div>
<!-- <r-m-list :characters="characters"></r-m-list> -->
<character-detail v-if="selectedCharacter" :character="selectedCharacter"></character-detail>
</div>
</template>

<script>
import Header from "./components/Header.vue"
import{eventBus} from './main.js'
import RMList from "./components/RMList.vue"
import CharacterDetail from './components/CharacterDetail.vue'
export default {
  name: "app",
  data() {
    return {
      characters: [],
      selectedCharacter :null
    }},

components:{
            "header-item": Header,
            "r-m-list": RMList,
            'character-detail': CharacterDetail,

},

methods:{

},
mounted(){
  fetch('https://rickandmortyapi.com/api/character/')
  .then(result => result.json()).then(characters => this.characters = characters.results)

  eventBus.$on('char-selected', (character) =>{
    this.selectedCharacter = character})
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
