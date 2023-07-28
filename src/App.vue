<script setup>
  import MovieHeader from './components/MovieHeader.vue';
  import MovieList from './components/MovieList.vue';
  import MovieFooter from './components/MovieFooter.vue';
  import useFetchMovieData from './composables/useFetchMovieData';

  // setup 스크립트는 컴포넌트 생성 시 단 한번만 수행됨
  // 따라서, 컴포넌트가 처음 생성될 때 수행되는 코드
  const {movies, fetchMovieData} = useFetchMovieData();
  fetchMovieData('now_playing');
  
  function handleLinkClick(e) {
    console.log(e);
    fetchMovieData(e);
  }

  function handleSearchInputType(e) {
    fetchMovieData(e);
  }
</script>

<template>
  <movie-header 
    @linkClick="handleLinkClick" 
    @searchInputType="handleSearchInputType"
  />
  <movie-list :movieList="movies"/>
  <movie-footer/>
</template>
