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
                <li><i class="fas fa-search"></i></li>
                <li>BAMBINI</li>
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
  
}
</script>

<style lang="scss">
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
