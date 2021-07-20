<template>

    <div class="col-6 col-sm-4 col-md-3 col-lg-2  spazio-sotto">
        <!-- Qua con il bind nello style, lo si collega ad una funzione sotto nei computed -->
        <div class="box-image" :style="image">
            <div class="descrizione">
                <div class="titolo">{{title}}</div> 
                <div class="serie">{{name}}</div> 
                <div class="original-title">{{original_title}}</div> 
                <!-- <div class="original-language">{{original_language}}</div>  -->
                
                <!-- Bandiere lingue -->
                <!-- <div class="lingua">
                    <flag iso="us" />
                </div> -->


                <div class="box-bandiera">
                    <img :src="bandiera(original_language)" :alt="original_language">
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
    components: {

    },
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
                return 'background-image: url(https://image.tmdb.org/t/p/w500/' + this.poster_path + ')';
            // Altrimenti mi restituisci un'altra copertina: 
            } else {
                // TODO SFONDO DA SISTEMARE PER QUELLI SENZA COPERTINA  
                return 'background:red'; 
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
            
        },
        bandiera (prova) {
            if(this.original_language === prova) {
                return require('../assets/' + this.original_language + '.png');
            }else {
                return require('../assets/error.png');
            }
        },
        
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
    .spazio-sotto{
        margin-bottom:24px;
    } 
</style>