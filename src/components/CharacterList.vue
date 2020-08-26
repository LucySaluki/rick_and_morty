<template>
  <div>
      <ul>
        <char-list-item v-for="(character, index) in characters" :character="character" :key="index"></char-list-item>
      </ul>
  </div>
</template>

<script>
import CharacterListItem from './CharacterListItem.vue';

export default {
    name: 'character-list',
    props: ['characters'],
    components: {
        "char-list-item": CharacterListItem
    }
}
</script>

<style>

</style>