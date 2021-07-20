<template>
  <div id="app">
    <Header @cerca = "searchMovie" />

    <Main :menuList="listaCercati" /> 
    <MainSerieTv :listaSerieTV="cercatiSerieTv"/> 

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

    // Chiamate per stampare a video
    // Chiamata per il film:
    axios.get('https://api.themoviedb.org/3/movie/popular?api_key=6ab3e57615f14eaaf5a85958841a5555').then((response) =>{
      this.menuList = response.data.results;
      this.listaCercati = response.data.results;
      console.log(this.menuList)
    });

    // Chiamata per le serie TV: 
    axios.get('https://api.themoviedb.org/3/tv/popular?api_key=6ab3e57615f14eaaf5a85958841a5555').then((response) =>{
        this.listaSerieTV = response.data.results;
        this.cercatiSerieTv = response.data.results;
        console.log(this.listaSerieTV)
    });
    
  },
  data: function() {
    return{
      menuList: [],
      listaCercati: [],
      listaSerieTV:[],
      cercatiSerieTv:[],
    }
  },
  methods: {
    searchMovie(searchString){
      // Chiamate per la ricerca: 
      if (searchString.length == 0 ) {
        // Se non c'è scritto niente nella barra di ricerca mi ripopoli la array originale, sia di film che serie tv:
        this.listaCercati = this.menuList; 
        this.cercatiSerieTv = this.listaSerieTV; 
        return 

      // Altrimenti se si scrive qualcosa, quindi c'è più di un carattere:
      }else if (searchString.length > 0) {
        axios.get(`https://api.themoviedb.org/3/search/tv?api_key=6ab3e57615f14eaaf5a85958841a5555&query=${searchString}`).then((response) =>{
        this.cercatiSerieTv = response.data.results;
        console.log(this.cercatiSerieTv)
        });

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
