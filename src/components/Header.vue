<template>
    <!-- WE CREATE A MINIMAL LAYOUT FOR VIEWING ONLY -->
    <header>
        <!-- CREATION A SECTION OF SEARCH -->
        <!-- WE GIVE A TEMPORARY REFERENCE CLASS THAT WE WILL USE IN THE FOLLOWING MILESTONES -->
        <div class="section_nav">
            <!-- CREATION AN INPUT -->
            <input type="text" placeholder="Search" v-model="getMovie">
            <!-- CREATION A BUTTON -->
            <button @click.prevent="$emit('getMovie', getMovie)">Search</button>
        </div>
    </header>
</template>


<script>
export default {
    name: 'Header',
    data(){
        return{
            getMovie: '',
        }
    }
}
</script>




<style lang="scss" scoped>
// ASSEGNARE DELLE CLASSI NELLE MILESTONE SUCCESSIVE PER RENDERE LA WEB APP PIU' CARINA
// HO DATO AL BOTTONE UN MINIMO DI STILI PER FARLO VEDERE
button {
  width: 70px;
  padding: 14px 10px;
  border-radius: 2px;
  background-color: red;
  color: white;
  cursor: pointer;
}
</style>