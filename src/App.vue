<template>
  <div id="app">
    <Header />
  </div>
</template>

<script>
import Header from './components/Header.vue'

export default {
  name: 'App',
  components: {
    Header,
  },
  created () {
    
  },
  data: function() {
    return{
      menuList: [
        {},
        {},
        {},
        {},
        {},
        {},
      ]
    }
  },
}
</script>

<style lang="scss">

@import './style/app.scss';

</style>
