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
// Collegamento con il componente card con all'interno tutti i dati dell'array, passati da qui con il promps:
import Card from './Card.vue';

export default {
    name:'MainSerieTv',
    components: {
        Card,
    },
    // Array passata da appvue a qui per poi farla utilizzare da card, tramite qui estraggo gli oggetti:
    props:{
        listaSerieTV: Array,
        starVote: Array,
    }
}

</script>


<style lang="scss" scoped>

    h3{
        color:white;
        margin-bottom:24px; 
    }

</style>