<template>
  <!-- WE CREATE A MINIMAL LAYOUT FOR VIEWING ONLY -->
  <header>
    <!-- CREATION A SECTION OF SEARCH -->
    <!-- WE GIVE A TEMPORARY REFERENCE CLASS THAT WE WILL USE IN THE FOLLOWING MILESTONES -->
    <div class="section_nav">
      <img class="header_img" src="../assets/img/boolflix.png" alt="" />
      <!-- CREATION AN INPUT -->
      <input
        type="text"
        placeholder="Title, people, genres"
        v-model="getMovie"
      />
      <!-- CREATION A BUTTON -->
      <button @click.prevent="$emit('getMovie', getMovie)">Search</button>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",
  data() {
    return {
      getMovie: "",
    };
  },
};
</script>

<style lang="scss" scoped>
header {
  width: 100%;
  background-color: black;
  height: 80px;
  display: flex;
  justify-content: center;
  align-items: center;
  top: 0;
  position: fixed;

  .header_img {
    width: 120px;
    display: flex;
  }
  button {
    width: 70px;
    border-radius: 2px;
    background-color: lightgray;
    color: black;
    cursor: pointer;
  }
}
</style>