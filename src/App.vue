<template>
  <div id="app">
    <Header @getMovie="getMovie"/>
    <Main :movies="movies" />
  </div>
</template>

<script>
import axios from 'axios';
import Header from '@/components/Header.vue';
import Main from '@/components/Main.vue';

export default {
  name: "App",
  components: {
    Header,
    Main
  },
  data() {
    return {
      apiURL: 'https://api.themoviedb.org/3/search/',
      apiKey: 'f9da0a6d03828e42d32c7eee44819c2d',
      movies: [],
    }
  },
  methods: {
    // Funzione che richiama l'API
    getMovie(search) {
      if(search !== '') {
        const apiParams = {
          api_key: this.apiKey,
          query: search,
        };
        //FILM
        axios.get(this.apiURL + 'movie', {
          params: apiParams,
            
        }).then(res => {
          this.movies = res.data.results;
        });
      }
    }
  }
};
    
</script>

<style lang="scss">
@import './styles/general';
</style>
