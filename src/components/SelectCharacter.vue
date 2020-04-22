<template lang="html">
  <div >
    <label for="character_select">Select a Character:</label>
    <select id="character_select" v-on:change="handleChoice" v-model="selectedChar">
      <option disabled value="">Select a Character</option>
      <option v-for="character in characters" :value="character" >{{character.name}}</option>
    </select>
    </div>
</template>

<script>
import {eventBus} from'../main.js'
export default {
  name: "SelectCharacter",
  props: ['characters'],
  data(){
    return{
      selectedChar: null
    }
  },
  methods:{
    handleChoice: function(){
      eventBus.$emit('input', this.selectedChar)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
