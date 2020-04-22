<template lang="html">
  <div>
  <li v-on:click="handleClick">{{character.name}}</li>
  </div>
</template>

<script>
import {eventBus} from'../main.js'
export default {
  name: 'RMItem',
  props: ["character"],
  methods: {
    handleClick: function(){
      eventBus.$emit('char-selected', this.character)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
