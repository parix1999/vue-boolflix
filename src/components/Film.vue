<template>
    <div class="col-2">
        <div class="box-image">
    
            <div class="prova">
                <div class="titolo">{{title}}</div> 
                <div class="original-title">{{original_title}}</div> 
                <div class="original-language">{{original_language}}</div> 
                <!-- Bandiere lingue -->
                <div class="box-bandiera" v-if="original_language === 'en' ">
                    <img src="../assets/en.png" alt="inglese">
                </div>
                <div class="box-bandiera" v-else-if="original_language === 'it' ">
                    <img src="../assets/it.png" alt="italiano">
                </div>
                <div class="box-bandiera" v-else-if="original_language === 'es' ">
                    <img src="../assets/es.png" alt="spagnolo">
                </div>
                <div class="box-bandiera" v-else-if="original_language === 'fr' ">
                    <img src="../assets/fr.png" alt="francese">
                </div>
                 <div class="box-bandiera" v-else-if="original_language === 'pt' ">
                    <img src="../assets/pr.png" alt="portoghese">
                </div>

                
                <div class="vote-average">{{vote_average}}</div> 
            </div>

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
       poster_path: String,  
    }
}

</script>


<style lang="scss" scoped>

    .box-image{
        background-image: url('https://image.tmdb.org/t/p/w342/hQq8xZe5uLjFzSBt4LanNP7SQjl.jpg');
        background-size:contain; 
        background-position:top;
        background-repeat: no-repeat;
        width:180px;
        height:300px;
        .prova{
            display: none;
        }
    &:hover .prova{
        display:block; 
        color:white; 
    }
        
    }
    .box-bandiera {
        width:50px;

        img{
            width:100%;
        }
    }


</style>