<template>
  <section class="box">
    <!-- title and description-->
    <div class="my_cards">
      <!-- Poster -->
      <img
        class="cover_img"
        :src="`https://image.tmdb.org/t/p/w342${type.poster_path}`"
        alt="Movie Poster"
      />
      <div class="info">
        <ul>
          <!-- Title -->
          <li>
            <!-- Attenzione qui, l'API ci manda i 2 valori tra Movies e Series diversi -->
            <strong>Titolo:{{ type.title ? type.title : type.name }}</strong>
          </li>
          <!-- Original Title -->
          <li>
            <!-- Attenzione qui, l'API ci manda i 2 valori tra Movies e Series diversi -->
            <strong
              >Titolo originale:{{
                type.original_title ? type.original_title : type.original_name
              }}</strong
            >
          </li>
          <!-- Lenguages -->
          <li class="flags">
            <img
              v-if="flagArray.includes(type.original_language)"
              :src="require(`../assets/img/${type.original_language}.png`)"
              :alt="type.original_language"
            />
            <span v-else>{{ type.original_language }}</span>
          </li>
          <!--vote-->
          <!-- MILESTONE 3 -->
          <li>
            <strong>Voto:</strong>
            <span v-for="val in getVote" :key="val"
              ><i class="fas fa-star star"></i
            ></span>
          </li>
          <!-- DESCRIPTION -->
          <li><strong>Overview:</strong>{{ type.overview }}</li>
          <li></li>
        </ul>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Movie",
  props: {
    type: Object,
  },
  // RITORNO DELLE FLAG
  data() {
    return {
      flagArray: ["en", "es", "it"],
    };
  },
  computed: {
    getVote() {
      return Math.ceil(this.type.vote_average / 2);
    },
  },
};
</script>

<style lang="scss" scoped>
.box {
  width: 20%;
  .my_cards {
    display: flex;
    flex-wrap: wrap;
    margin-top: 50px;
    flex-shrink: 0;
    padding: 30px;
    width: 100%;
    .flags {
      width: 28px;
      img {
        width: 100%;
      }
      .lenguages {
        margin-left: 10px;
        font-size: 18px;
      }
    }

    .cover_img {
      width: 100%;
    }

    .star {
      color: yellow;
    }
    .info {
      display: none;
      padding: 30px;
    }
  }
  .my_cards:hover {
    padding: 10px;
  }
  .my_cards:hover .cover_img {
    display: none;
  }
  .my_cards:hover .info {
    display: block;
  }
}
</style>