<template>
  <div>
    <h1>Rick and Morty</h1>
    <div class="main-container">
    <characters-list :characters='characters'></characters-list>
    <character-detail :character='selectedCharacter'></character-detail>
  </div>
  </div>
</template>

<script>
import CharactersList from './components/CharacterList.vue';
import CharacterDetail from './components/CharacterDetail.vue';
import { eventBus } from './main.js';

export default {
  name: 'app',
  data(){
    return {
      characters: [],
      selectedCharacter: null
    };
  },
  mounted(){
    fetch('https://rickandmortyapi.com/api/character')
    .then(results => results.json())
    .then(characters => this.characters = characters.results)

    eventBus.$on('character-selected', (character) => {
      this.selectedCharacter = character
    })
  },
  components: {
    "characters-list": CharactersList,
    "character-detail": CharacterDetail
  }

}
</script>

<style>
  .main-container {
    display: flex;
    justify-content: space-between;
  }
</style>
