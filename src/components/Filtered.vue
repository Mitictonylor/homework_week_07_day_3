<template lang="html">
  <div>
    <h3>Filter characters</h3>
    <input v-on:input:"changeList"type="text" v-model="char" value='' placeholder="start to type" >
  </div>
</template>

<script>
import {eventBus} from'../main.js'
export default {
  name:"Filtered",
  data(){
    return{
      char:""
    }
  },
  props:["characters"],
  computed:{
    filteredCharacters: function(){
return this.characters.filter((character) => { return character.name.match(this.char)})
    }
    // changeList(){
    //   eventBus.$emit('filtered-array', this.filteredCharacters)
    // }
  }
}
</script>

<style lang="css" scoped>
</style>
