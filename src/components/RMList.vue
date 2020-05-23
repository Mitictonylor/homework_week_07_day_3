<template lang="html">
<div>
  <div>
    <h3>Filter characters</h3>
    <input type="text" v-model="char" value='' placeholder="start to type" >
  </div>
  <ul>
    <list-item v-for="(character,index) in filteredCharacters" :character="character" :key="index"></list-item>
  </ul>

</div>
</template>

<script>
// import {eventBus} from'../main.js'
import RMItem from './RMItem.vue'
export default {

  name: "RMList",
  props: ["characters"],
  components: {
    'list-item': RMItem
  },
  data(){return{
    char:"",
    filteredArray: []
  }},
  computed:
  {
    filteredCharacters: function(){
return this.characters.filter((character) => { return character.name.match(this.char)})
    }
  },
  mounted(){
    // eventBus.$on('filtered-array', (array) =>{
    //   this.filteredArray = array})
  }
}
</script>

<style lang="css" scoped>
</style>
