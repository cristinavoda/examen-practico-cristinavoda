<!-- src/components/FilmsList.vue -->
<template>
  <div class="p-4">
    <h1 class="text-2xl font-bold">Star Wars Films</h1>
    <ul>
      <li v-for="film in Films" :key="film.episode_id" @click="showDetails(film)">
        {{ film.title }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: ['films'],
  methods: {
    showDetails(movie) {
      this.$emit('show-details', film);
    },
  },
};
</script><!-- src/components/FilmDetail.vue -->
<template>
  <div class="p-4">
    <h2 class="text-xl font-bold">{{ film.title }}</h2>
    <p>Episode: {{ film.episode_id }}</p>
    <p>Director: {{ film.director }}</p>
    <p>Release Date: {{ film.release_date }}</p>
</template>

<script>
async function request() {
    const response = await fetch ("https://swapi.dev/api/films/")
    const data = await response.json()
} 
</script>

