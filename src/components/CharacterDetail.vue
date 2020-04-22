<template lang="html">
  <div>


<img :src="character.image"  >
<p>Name: {{character.name}}</p>
<p>Specie: {{character.species}}</p>
<p>Status: {{character.status}}</p>
<p>Origin: {{character.origin.name}}</p>
</div>
</template>

<script>
export default {
  name: 'CharacterDetail',
  props: ['character']
}
</script>

<style lang="css" scoped>
</style>
