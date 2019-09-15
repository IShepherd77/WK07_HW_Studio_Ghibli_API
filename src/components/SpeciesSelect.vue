<template lang="html">
  <div>
  <select v-model="SpeciesSelected" v-on:select="handleSelect">
    <option v-for="species in speciesList" v-bind:value="species">
      {{ species.name}}
    </option>
  </select>
</div>
</template>

<script>

import { eventBus } from '../main.js'

export default {
  name: 'species-select',
  props: ['speciesList'],

  methods: {handleSelect: function handleSelect(event){
    console.log(event);
    eventBus.$emit('species-selected', event.target.value)
  }
},
data(){
    return {
      "SpeciesSelected": {}
    }
  }
}

</script>
<style lang="css" scoped>
</style>
