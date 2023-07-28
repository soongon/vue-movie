<script setup>
  import { computed } from 'vue';

  const props = defineProps(['movie']);

  const imgSrc = computed(() => {
    return props.movie.poster_path 
                    ? `https://image.tmdb.org/t/p/w500${props.movie.poster_path}` 
                    : `https://image.tmdb.org/t/p/original/wwemzKWzjKYJFfCeiB57q3r4Bcm.svg`;
  });
  
</script>

<template>

  <div class="max-w-sm bg-white border border-gray-200 rounded-lg shadow m-3 dark:bg-gray-800 dark:border-gray-700">
      <a href="#">
          <img class="rounded-t-lg" :src="imgSrc" alt="" />
      </a>
      <div class="p-5">
          <a href="#">
              <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">{{ movie.title }}</h5>
          </a>
          <p class="mb-3 font-normal text-gray-700 dark:text-gray-400">{{ movie.overview ? movie.overview : '내용 없음' }}</p>
          
      </div>
  </div>

</template>