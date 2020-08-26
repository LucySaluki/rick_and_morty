<template>
  <div v-if='selectedCharacter'>
    <img :src="selectedCharacter.image" >
    <h2>Name: {{selectedCharacter.name}}</h2>
    <p>Species: {{selectedCharacter.species}}</p>
    <p>Status: {{selectedCharacter.status}}</p>
    <p>Origin: {{ selectedCharacter.origin.name }}</p>
  </div>
</template>

<script>
export default {
  name: "char-detail",
  props: ["selectedCharacter"],
};
</script>

<style>
img {
    width: 100px;
    border-radius: 50%;
}
</style>