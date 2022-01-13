<template>
    <section class="box">
        <!-- title and description-->
        <div class="my_cards">
            <div>
                <!-- Poster -->
                 <img :src="`https://image.tmdb.org/t/p/w342${type.poster_path}`" alt="Movie Poster">
            </div>
            
             <ul>
                <!-- Title -->
                <li>
                    <!-- Attenzione qui, l'API ci manda i 2 valori tra Movies e Series diversi -->
                    <strong>Titolo:{{type.title ? type.title : type.name}}</strong>
                </li>
                <!-- Original Title -->
                <li>
                      <!-- Attenzione qui, l'API ci manda i 2 valori tra Movies e Series diversi -->
                    <strong>Titolo originale:{{type.original_title ? type.original_title : type.original_name}}</strong>
                </li>
                <!-- Lenguages -->
                <li class="flags">
                    <img v-if="flagArray.includes(type.original_language)" :src="require(`../assets/img/${type.original_language}.png`)" :alt="original_language">
                    <span v-else>{{ type.original_language }}</span>
                </li>
                <!--vote-->
                <!-- MILESTONE 3 -->
                 <li>
                    <strong>Voto:</strong>  
                    <span v-for="val in getVote" :key="val"><i class="fas fa-star"></i></span>            
                </li>
               <!-- DESCRIPTION -->
                <li>
                    <strong>Overview:</strong>{{type.overview}}
                </li>
                <li></li>
            </ul>
        </div>
    </section>
</template>

<script>
export default {
     name: 'Movie',
     props: {
        type: Object,
    },
    // RITORNO DELLE FLAG
    data() {
        return{
            flagArray:['en', 'es', 'it'],
        }
    },
    computed:{
        getVote(){
            return Math.ceil(this.type.vote_average/2);
        }
    }
}

</script>

<style lang="scss" scoped>
.box {
    display: flex;
    flex-wrap: wrap;
    .my_cards{
         width: calc((100% / 3) - 40px);
         margin: 10px 20px;
            .flags{
                width: 28px;
                display: flex;
                img{
                    width: 100%;
                }
            }
    }
}

</style>