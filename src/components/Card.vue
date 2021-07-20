<template>

    <div class="col-6 col-sm-4 col-md-3 col-lg-2">
        <!-- Qua con il bind nello style, lo si collega ad una funzione sotto nei computed -->
        <div class="box-image" :style="image">
            <div class="descrizione">
                <div class="titolo">{{title}}</div> 
                <div class="serie">{{name}}</div> 
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
                

                <div v-else>
                    <div class="warning">Nessuna bandiera per questa lingua, scusate</div>
                </div>

                
                <div class="vote-average" >
                    <i v-for="n in 5" :key="n" :class="vote(n)"></i>

                </div>

            </div>

        </div>

    </div>

</template>


<script>


export default {
    name:'Card',
    props: {
       title: String,
       original_title: String, 
       original_language: String,
       vote_average: Number,
       poster_path: String,  
    //Dati serie TV:
        name: String,

        starVote: Array, 

    },
   
    computed: {
        // Funzione collegata allo style sopra, quindi si possono passare proprietà del css
        image() {
            // Se poster_path non è null e ha un valore allora mi ritorni l'url dell'immagine che c'è nella array:
            if (this.poster_path) {
                return 'background-image: url(https://image.tmdb.org/t/p/w500/' + this.poster_path + ');';
            // Altrimenti mi restituisci un'altra copertina: 
            } else {
                return 'background-image: url(../assets/error.png)'; 
            }
        },
        
        

    },
    methods: {
        vote(numeroIterazione) {
            let calc = Math.ceil(this.vote_average / 2);
            if (numeroIterazione <= calc ){
                return 'fas fa-star '
            } else {
                return 'far fa-star'
            }
            
        }
    }
}

</script>


<style lang="scss" scoped>

    .box-image{
        background-size:cover; 
        background-position:top;
        background-repeat: no-repeat;
        width:100%;
        height:300px;

        .descrizione{
            display: none;
            background-color:rgba(0, 0, 0, .7);
            height:100%;

        }
    &:hover .descrizione{
        display:block; 
        color:white;
        cursor: pointer; 
    }
        
    }
    .box-bandiera {
        width:20px;

        img{
            width:100%;
        }
    }
    .warning{
        font-size: 10px;
    }


</style>