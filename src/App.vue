<template>
  <div>
    <h1>Rick and Morty Characters</h1>
    <main>
      <label for="char_select">Select a Character:</label>
      <select id="char_select" v-model="selectedCharacter">
      <option disabled value>Select a Character</option>
      <option v-for="(character, index) in characters" :key="index" :value="character">{{character.name}}</option>
      </select>
      <!-- <character-list :characters="characters"></character-list> -->
      <char-details :selectedCharacter='selectedCharacter'></char-details>
    </main>
  </div>
</template>

<script> 
import { eventBus } from './main';
import CharacterList from './components/CharacterList.vue';
import CharacterDetail from './components/CharacterDetail.vue';

export default {
  name: 'app',
  data() {
    return {
      characters: [], 
      selectedCharacter: null
    }
  },
  mounted(){
    fetch('https://rickandmortyapi.com/api/character')
    .then(res => res.json())
    .then(characters => this.characters = characters.results)

    eventBus.$on('char-selected', (character) => {
      this.selectedCharacter = character;
    })
  },
  components: {
    "character-list": CharacterList,
    "char-details": CharacterDetail
  }
}
</script>

<style>
  body {
    font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
    padding:10px;
  }
</style>