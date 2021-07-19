<template>
  <div id="app">
    <Header @cerca = "searchMovie"/>

    <Main :menuList="listaCercati"/> 

  </div>
</template>

<script>
import axios from 'axios';

import Header from './components/Header.vue';
import Main from './components/Main.vue';

export default {
  name: 'App',
  components: {
    Header,
    Main,
  },
  created () {
    axios.get('https://api.themoviedb.org/3/movie/popular?api_key=6ab3e57615f14eaaf5a85958841a5555').then((response) =>{
      this.menuList = response.data.results;
      this.listaCercati = response.data.results;
      console.log(this.menuList)
    });
  },
  data: function() {
    return{
      menuList: [],
      listaCercati: [],
    }
  },
  methods: {
    searchMovie(searchString){
      if (searchString.length == 0 ) {
        this.listaCercati = this.menuList; 
        return 
      } else {
        axios.get(`https://api.themoviedb.org/3/search/movie?api_key=6ab3e57615f14eaaf5a85958841a5555&query=${searchString}`).then((response) =>{
        this.listaCercati = response.data.results;
        console.log(this.listaCercati)

        });

      }
    }
  }
}
</script>

<style lang="scss">

@import './style/app.scss';

</style>
