<template>
    <div class="container personalized">
        <div class="row">
            <Film v-for="(film, index) in menuList" :key="index" 
            :poster_path="film.poster_path"
            :title="film.title"
            :original_title="film.original_title"
            :original_language="film.original_language"
            :vote_average="film.vote_average"/>

        </div>
    </div>
</template>


<script>
import Film from './Film.vue'

export default {
    name:'Main',
    components:{
        Film,
    },
    props:{
        menuList: Array,
        
    }
    
}

</script>


<style lang="scss" scoped>

    .personalized{
        margin-top:50px;
    }

</style>