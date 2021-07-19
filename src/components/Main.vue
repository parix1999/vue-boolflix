<template>
    <div class="container">
        <div class="row">
            <Film v-for="(film, index) in menuList" :key="index" />

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

</style>