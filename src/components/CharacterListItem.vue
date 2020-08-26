<template>
  <li v-on:click="handleClick">{{character.name}}</li>
</template>

<script>
import { eventBus } from '../main.js'
export default {
    name: 'char-list-item',
    props: ['character'],
    methods: {
        handleClick() {
            eventBus.$emit('char-selected', this.character)
        }
    }
}
</script>

<style>

</style>