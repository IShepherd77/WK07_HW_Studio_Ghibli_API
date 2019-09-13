<template>
  <div id="app">
    <h1>Ghibli Films</h1>
    <div>
      <film-detail v-bind:film="selectedFilm"></film-detail>
      <species-select v-bind:speciesList="speciesList"></species-select>
      <films-list v-bind:films="films"></films-list>
    </div>
  </div>
</template>

<script>
import FilmsList from './components/FilmsList.vue';
import FilmDetail from './components/FilmDetail.vue';
import SpeciesSelect from './components/SpeciesSelect.vue';
import { eventBus } from "./main.js";

export default {
  name: 'app',
  data(){
    return {
      films: [],
      selectedFilm: null,
      speciesList: []
    };
  },
  mounted(){
    fetch('https://ghibliapi.herokuapp.com/films')
    .then(result => result.json())
    .then(films => this.films = films)

    fetch('https://ghibliapi.herokuapp.com/species?fields=id,name')
    .then(result => result.json())
    .then(speciesList => this.speciesList = speciesList)

    eventBus.$on('film-selected', (film) => {
      this.selectedFilm = film
    })
  },
  components: {
    "films-list": FilmsList,
    "film-detail": FilmDetail,
    "species-select": SpeciesSelect
  }
}
</script>

<style lang="css" scoped>
</style>
