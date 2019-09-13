<template lang="html">
  <select v-model="selectedSpecies">
    <option v-for="species in speciesList" v-bind:value="species">
      {{ species.name}}
    </option>


  </select>
</template>

<script>

export default {
  name: 'species-select',
  props: ['speciesList']
  }

</script>
<style lang="css" scoped>
</style>
