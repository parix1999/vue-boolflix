<template>
    <nav>
        <div class="box-logo">
            <img src="../assets/netflix-logo.png" alt="Logo">
        </div>
        <ul>
            <li><a href="#">Home</a></li>
            <li><a href="#">Serie TV</a></li>
            <li><a href="#">Film</a></li>
            <li><a href="#">Originali</a></li>
            <li><a href="#">Aggiunti di recente</a></li>
            <li><a href="#">La mia lista</a></li>
            
        </ul>

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
            align-items: center;
            margin:0;

            li a{
                text-decoration:none; 
                padding : 0 10px;
                color: gray; 
                
                &:hover{
                    color:white; 
                }
            }
        }

    }

</style>
