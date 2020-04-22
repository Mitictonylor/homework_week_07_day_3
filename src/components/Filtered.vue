<template lang="html">
  <div>
    <h3>Filter characters</h3>
    <input type="text" v-model="char" value='' placeholder="start to type" >
  </div>
</template>

<script>
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
  }
}
</script>

<style lang="css" scoped>
</style>
