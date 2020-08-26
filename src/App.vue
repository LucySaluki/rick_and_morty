<template>
  <div>
    <h1>Rick and Morty Characters</h1>
    <main>
      <character-list :characters="characters"></character-list>
    </main>
  </div>
</template>

<script> 
import CharacterList from './components/CharacterList.vue';

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
  },
  components: {
    "character-list": CharacterList
  }
}
</script>

<style>
</style>