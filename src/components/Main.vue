<template>
    <div class="container personalized">
        <div class="row">
            <h3>Film:</h3>
            <Card v-for="(film, index) in menuList" :key="index" 
            :poster_path="film.poster_path"
            :name="film.name"
            :title="film.title"
            :original_title="film.original_title"
            :original_language="film.original_language"
            :vote_average="film.vote_average"/>
          
            
        </div>
    </div>
</template>


<script>
import Card from './Card.vue';


export default {
    name:'Main',
    components:{
        Card,
        
    },
    props:{
        menuList: Array,
        
        
    }
    
}

</script>


<style lang="scss" scoped>

    .personalized{
        margin-top:50px;
        h3{
            color:white;
            margin-bottom:24px;
        }
    }

</style>