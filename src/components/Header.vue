<template>
    <nav>
        <!-- logo -->
        <div class="box-logo">
            <img src="../assets/netflix-logo.png" alt="Logo">
        </div>
        <!-- lista link -->
        <ul>
            <li><a href="#">Home</a></li>
            <li><a href="#">Serie TV</a></li>
            <li><a href="#">Film</a></li>
            <li><a href="#">Originali</a></li>
            <li><a href="#">Aggiunti di recente</a></li>
            <li><a href="#">La mia lista</a></li>
            
        </ul>
        <!-- icona cerca e profilo -->
        <div>
            <ul>
                <li>
                    <input :class="noVisualiza()" v-model="searchString" placeholder="Search" 
                    @keyup.enter="$emit('cerca', searchString)">

                </li>
                <!-- Icona ricerca: -->
                <li  @click="$emit('visualizza')">

                    <i class="fas fa-search puntatore"></i>

                </li>
                <!-- Scritta -->
                <li>BAMBINI</li>
                <!-- Icona campana -->
                <li><i class="fas fa-bell"></i></li>
                <li>
                    <div class="box-account">
                        <img src="../assets/account-photo.png" alt="utente photo">

                    </div>
                </li>
                <li><i class="fas fa-sort-down"></i></li>

            </ul>

        </div>

    </nav>
</template>

<script>


export default {
  name: 'Header',
  props:{
        flag: Boolean,
    },


  data:function(){
      return{
        searchString: '',
          
    }
  },

  methods: {
    
    noVisualiza() {
        if (this.flag == true){
            return 'noVisual';
        } else {
            return 'visual';
        }

    }



  },
}
</script>

<style lang="scss">

//barra ricerca: 

    .noVisual {
        display: none;
    }
    .visual{
        display: block;
    }
    // Classe per il puntatore on click:
    .puntatore {
        cursor: pointer;
    }


//--------------------

    nav {
        background-color:black; 
        padding: 5px 0 10px 10px;
        display: flex;
        align-items:center; 
        justify-content: space-between;
        

        .box-logo {
            width:150px;
            
            img {
                width:100%;
            }
        }

        ul {
            list-style-type: none;
            padding: 0 25px;
            display: flex;
            margin:0;
            flex-grow:1;

            li{
                padding:0 10px;
                color:white; 
            }

            li a{
                text-decoration:none; 
                color: gray; 

                &:hover{
                    color:white; 
                }
            }
        }

        .box-account{
            width: 50px;
            img {
                width:100%;
            }
        }

    }

</style>
