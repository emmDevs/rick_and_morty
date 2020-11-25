<template>
  <div v-if="character">
      <h3>{{ character.name }}</h3>
      <p>{{ character.species }}</p>
      <p>{{ character.status }}</p>
      <img :src="character.image">
  </div>
  <div v-else>
      <p>Please choose a character!</p>
  </div>
</template>

<script>
export default {
    name: 'character-detail',
    props: ['character']
}
</script>

<style>

</style>