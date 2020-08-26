<template>
  <div v-if='selectedCharacter'>
    <h2>{{selectedCharacter.name}}</h2>
    <p>{{selectedCharacter.species}}</p>
    <p>{{selectedCharacter.status}}</p>
  </div>
</template>

<script>
export default {
  name: "char-detail",
  props: ["selectedCharacter"],
};
</script>

<style>
</style>