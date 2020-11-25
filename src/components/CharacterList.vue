<template>
  <div>
      <ul>
          <list-item v-for="character in characters" :character="character" :key="character.id"></list-item>
      </ul>
  </div>
</template>

<script>
import ListItem from './ListItem'

export default {
    name: 'characters-list',
    props: ['characters'],
    components: {
        "list-item": ListItem
    }
}
</script>

<style>

</style>