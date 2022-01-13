<template>
  <!--FILM SECTION-->
  <main>
    <div v-if="movies.length > 0 || tv.length > 0">
      <h2>Film</h2>
      <div class="cards_container">
        <Movie v-for="movie in movies" :key="movie.id" :type="movie" />
      </div>
      <!-- SERIETV SECTION -->
      <h2>Tv Show</h2>
      <div class="cards_container">
        <Movie v-for="serie in tv" :key="serie.id" :type="serie" />
      </div>
    </div>

    <div v-else>
      <h2>
        Welcome to Boolflix, where you can watch movies and TV series, to do so
        just write the name in the search bar. Enjoy your movies / tv series and
        come back soon ...
      </h2>
    </div>
    <div class="creator">
      <h2>
        Created by Vincenzo Piparo... <i class="fas fa-smile icon"></i>
        <img src="../assets/img/creator.png" alt="" />
      </h2>
    </div>
  </main>
</template>

<script>
import Movie from "../components/Movie.vue";
export default {
  name: "Main",
  components: {
    Movie,
  },
  props: {
    movies: Array,
    tv: Array,
  },
};
</script>

<style lang="scss" scoped>
// ASSEGNARE DELLE CLASSI NELLE MILESTONE SUCCESSIVE PER RENDERE LA WEB APP PIU' CARINA
main {
  margin-top: 80px;
  font-family: sans-serif;
}
.cards_container {
  display: flex;
  flex-wrap: wrap;
  background-color: #141414;
  color: white;
}
.icon {
  color: blue;
}
.creator h2 {
  margin: 30px;
  text-align: center;
}
.creator img {
  width: 150px;
  margin: 25px;
  border-radius: 10px;
  vertical-align: middle;
}
</style>
