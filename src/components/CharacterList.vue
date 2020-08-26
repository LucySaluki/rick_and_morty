<template>
  <div>
    <ul>
        <list-item v-for="(character, index) in characters" :character="character" :key="index"></list-item>
    </ul>
  </div>
</template>

<script>
import { eventBus } from '../main.js'
import CharacterListItem from "./CharacterListItem.vue";

export default {
  name: "character-list",
  props: ["characters"],
  components: {
    "char-list-item": CharacterListItem,
  }
};
</script>

<style>
</style>