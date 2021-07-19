<template>
    <div class="col-4">
        <div class="box-image">
            <div class="prova">ciao</div> 
        </div>

    </div>

</template>


<script>


export default {
    name:'Film',
    props: {
       title: String,
       original_title: String, 
       original_language: String,
       vote_average: Number, 
    }
}

</script>


<style lang="scss" scoped>

    .box-image{
        background-image: url('https://image.tmdb.org/t/p/w342/hQq8xZe5uLjFzSBt4LanNP7SQjl.jpg');
        width:342px;
        height:513px;
        .prova{
            display: none;
        }
    &:hover .prova{
        display:block; 
        color:white; 
    }
        
    }


</style>