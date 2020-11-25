<template>
  <div v-on:click="handleClick">
      <li>{{character.name}}</li>
      <img :class="avatar" :src="character.image">
  </div>
</template>

<script>
import { eventBus } from "../main.js";

export default {
    name: 'list-item',
    props: ['character'],
    methods: {
        handleClick(){
            eventBus.$emit('character-selected', this.character)
        }
    }

}
</script>

<style>

img{
    width:100px;
}

</style>