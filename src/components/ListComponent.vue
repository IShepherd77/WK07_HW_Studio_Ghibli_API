<template lang="html">
    <li v-on:click="handleClick">{{ film.title }}({{ film.release_date}})</li>
</template>

<script>
import { eventBus } from '../main.js'

export default {
  name: 'list-component',
  props: ['film'],
  methods: {
    handleClick(){
      eventBus.$emit('film-selected', this.film)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
