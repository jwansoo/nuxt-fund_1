<template>
  <div>
  <form @submit.prevent="search">
    <input type="text" v-model="query" />
    <button>Search</button>
  </form>
  <ul class=" flex flex-wrap gap-3 list-none">
    <li v-for="movie in movies" :key="movie.imdbID">
      <nuxt-link :to="{name:'movies-id',params:{id:movie.imdbID}}">
        <img :src="movie.Poster" :alt="movie.title" class=" w-28"/>
      </nuxt-link>
      <!-- {{ movie }} -->
    </li>
  </ul>
</div>
</template>

<script setup>
const query=ref('batman')
const movies=ref([])
async function search() {
  const { Search } = await $fetch(
   `http://www.omdbapi.com/?apikey=8e3f600b&s=${query.value}`
  );
  movies.value = Search;
}
search()
</script>

<style scoped>

</style>