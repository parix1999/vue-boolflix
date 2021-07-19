<template>
  <div id="app">
    <Header @cerca = "searchMovie" />

    <Main :menuList="listaCercati" /> 
    <MainSerieTv :listaSerieTV="listaSerieTV"/> 

  </div>
</template>

<script>
import axios from 'axios';

import Header from '@/components/Header.vue';
import Main from '@/components/Main.vue';
import MainSerieTv from '@/components/MainSerieTV.vue';


export default {
  name: 'App',
  components: {
    Header,
    Main,
    MainSerieTv,
    
  },
  created () {
    // Chiamata per il film:
    axios.get('https://api.themoviedb.org/3/movie/popular?api_key=6ab3e57615f14eaaf5a85958841a5555').then((response) =>{
      this.menuList = response.data.results;
      this.listaCercati = response.data.results;
      console.log(this.menuList)
    });

    // Chiamata per le serie TV: 
    axios.get(`https://api.themoviedb.org/3/search/tv?api_key=6ab3e57615f14eaaf5a85958841a5555&query=scrubs`).then((response) =>{
        this.listaSerieTV = response.data.results;
        console.log(this.listaSerieTV)
    });
    
  },
  data: function() {
    return{
      menuList: [],
      listaCercati: [],
      listaSerieTV:[],
    }
  },
  methods: {
    searchMovie(searchString){
      if (searchString.length == 0 ) {
        this.listaCercati = this.menuList; 
        return 
      }else if (searchString.length > 0) {
        axios.get(`https://api.themoviedb.org/3/search/movie?api_key=6ab3e57615f14eaaf5a85958841a5555&query=${searchString}`).then((response) =>{
        this.listaCercati = response.data.results;
        console.log(this.listaCercati)

        });
      } else {
        axios.get(`https://api.themoviedb.org/3/search/tv?api_key=6ab3e57615f14eaaf5a85958841a5555&query=${searchString}`).then((response) =>{
        this.listaSerieTV = response.data.results;
        console.log(this.listaSerieTV)
        

        });
      }
    }
  }
}
</script>

<style lang="scss">

@import './style/app.scss';

</style>
