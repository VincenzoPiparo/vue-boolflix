<template>
    <section class="box">
        
        <!-- title and langs-->
        <ul>
            <li>
                <strong>Titolo:{{ type.title}}</strong>
                
            </li>
            
            <li>
                <strong>Titolo originale:{{ type.original_title}}</strong>
                
            </li>

            <li>
                <strong>Lingua:{{type.original_language}}</strong>
            </li>

            <!--vote-->
            <li>
                <strong>Voto:{{type.vote_average}}</strong>              
            </li>
        </ul>
    </section>
</template>

<script>
export default {
     name: 'Movie',
     props: {
        type: Object,
    },
}

</script>

<style lang="scss" scoped>
.box {
    height: 500px;
    width: 350px;
    margin: 0 5px 0 20px;
    overflow: hidden;
    cursor: pointer;
    position: relative;  
}

</style>