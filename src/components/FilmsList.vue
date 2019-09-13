<template>
  <div>
    <ol>
      <list-component v-for="(film, index) in films" v-bind:film="film"
      v-bind:key="index"></list-component>
    </ol>
  </div>
</template>

<script>
import ListComponent from './ListComponent.vue';

export default {
  name: 'films-list',
  props: ['films'],
  components: {
    "list-component": ListComponent
  }
}
</script>
<style lang="css" scoped>
</style>
