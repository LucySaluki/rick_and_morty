<template>
  <div>
    <label for="char_select">Select a Character:</label>
    <select id="char_select" v-on:change="handleChange" v-model="selectedCharacter">
      <option disabled value>Select a Character</option>
      <option
        v-for="(character, index) in characters"
        :key="index"
        :value="character"
      >{{character.name}}</option>
    </select>
  </div>
</template>

<script>
import { eventBus } from '../main.js'
import CharacterListItem from "./CharacterListItem.vue";

export default {
  name: "character-list",
  data(){
      return {
        selectedCharacter: null
      }
  },
  props: ["characters"],
  components: {
    "char-list-item": CharacterListItem,
  },
  methods: {
        handleChange() {
            eventBus.$emit('char-selected', this.selectedCharacter)
        }
  }
};
</script>

<style>
</style>