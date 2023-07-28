<script setup>
  import MovieCard from './MovieCard.vue';

  defineProps(['movieList']);
</script>

<template>
  <main class="dark:bg-slate-700">
    <section class="max-w-7xl mx-auto py-7">
      <div class="flex justify-start flex-wrap">
        <movie-card 
          v-for="movie in movieList" 
          :key="movie.id"
          :movie="movie"
        />
      </div>
    </section>
  </main>
</template>

<style scoped>

</style>
