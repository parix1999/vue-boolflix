<template>
    <div class="container">
        <div class="row">
            <h3>Serie Tv:</h3>
            <!-- Serie tv: -->
            <Card v-for="(serie, index) in listaSerieTV" :key="index" 
            :poster_path="serie.poster_path"
            :name="serie.name"
            :title="serie.title"
            :original_title="serie.original_title"
            :original_language="serie.original_language"
            :vote_average="serie.vote_average"/>
          

        </div>

    </div>
</template>

<script>

import Card from './Card.vue';

export default {
    name:'MainSerieTv',
    components: {
        Card,
    },
    props:{
        listaSerieTV: Array,
    }
}

</script>


<style lang="scss" scoped>

    h3{
        color:white;
        margin-bottom:24px; 
    }

</style>