<template>
  <article v-if="film">
    <p>Title: {{ film.title }}</p>
    <p>Description: {{film.description}}</p>
    <p>Director: {{ film.director }}</p>
    <p>Release Year: {{film.release_date }}</p>
  </article>
</template>

<script>
export default {
  name: 'film-detail',
  props: ['film']
}
</script>

<style lang="css" scoped>
article {
  background-color: #f4f4f4;
}

p {
  color: darkblue;
  padding: 10px;
  font-size: 20px;
  font-weight: bold;
  font-family: Arial, sans-serif;
  text-shadow: 1px 1px 1px white;
}
</style>
