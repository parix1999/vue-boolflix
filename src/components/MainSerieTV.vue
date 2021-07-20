<template>
    <div class="container">
        <div class="row">
            <h3>Serie Tv:</h3>
            <!-- Serie tv: -->
            <SerieTv v-for="(serie, index) in listaSerieTV" :key="index" :name="serie.name"/>

        </div>

    </div>
</template>

<script>

import SerieTv from './SerieTv.vue';

export default {
    name:'MainSerieTv',
    components: {
        SerieTv,
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