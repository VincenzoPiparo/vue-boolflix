<template>
     <!--FILM-->
    <section v-show="movies.length" class="movies">
      <h2>Film</h2>
         <ul>
           <li
               v-for="movie in movies" 
              :key="movie.id">
              <Movie
              :type="movie"
              />
          </li>
         </ul>
    </section>
</template>

<script>
import Movie from '../components/Movie.vue';
export default {
  name: 'Main',
  components: {
    Movie
  },
  props: {
    movies: Array,
  }
}
</script>

<style lang="scss" scoped>
// ASSEGNARE DELLE CLASSI NELLE MILESTONE SUCCESSIVE PER RENDERE LA WEB APP PIU' CARINA
</style>
