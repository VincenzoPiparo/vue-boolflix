<template>
     <!--FILM SECTION-->
    <main>
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
     <!-- SERIETV SECTION -->
         
            <h2>Tv Show</h2>
                <ul>
                    <li
                    v-for="serie in tv" 
                    :key="serie.id">
                    <Movie 
                    :type="serie"
                    />
                    </li>
                </ul>
    </main>
       
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
    tv: Array,
  }
}
</script>

<style lang="scss" scoped>
// ASSEGNARE DELLE CLASSI NELLE MILESTONE SUCCESSIVE PER RENDERE LA WEB APP PIU' CARINA
main{
    display: flex;
    flex-wrap: wrap;
    ul{
        margin-top: 75px;
    }
}
</style>
