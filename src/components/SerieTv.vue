<template>
    <div class="col-2">
        
        <div class="box-image">
            <div class="name">
                {{name}}
            </div>

        </div>

       

    </div>
</template>


<script>


export default {
    name:'SerieTv',
    props:{
        name: String
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
    }
    .name{
        color:white; 
    }

</style>