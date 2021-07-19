<template>
  <div id="app">
    <Header />

    <Main :menuList="menuList"/> 

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
    axios.get('https://api.themoviedb.org/3/search/movie?api_key=6ab3e57615f14eaaf5a85958841a5555&query=ritorno+al+futuro').then((response) =>{
      this.menuList = response.data.results;
      console.log(this.menuList)
    });
  },
  data: function() {
    return{
      menuList: [],
    }
  },
}
</script>

<style lang="scss">

@import './style/app.scss';

</style>
