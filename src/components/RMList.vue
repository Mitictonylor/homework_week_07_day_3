<template lang="html">
<div>
  <ul>
    <list-item v-for="(character,index) in characters" :character="character" :key="index"></list-item>
  </ul>

</div>
</template>

<script>
import RMItem from './RMItem.vue'
export default {

  name: "RMList",
  props: ["characters"],
  components: {
    'list-item': RMItem
  }
}
</script>

<style lang="css" scoped>
</style>
