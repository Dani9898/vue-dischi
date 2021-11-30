<template>
  <div id="app">

    <Header :generi="listaGeneri" @search="getGenreValue" />

    <Dischi :genreToSearch="genreValue" @generiList="getGeneriList" />

  </div>
</template>

<script>
import Header from './components/Header.vue'
import Dischi from './components/Dischi.vue'

export default {
  name: 'App',
  components: {
    Header,
    Dischi
  },
  data() {
    return {
      listaGeneri: [],
      genreValue: ""
    }
  },
  methods: {
    getGeneriList(allGenres) {
      this.listaGeneri = allGenres
    },
    getGenreValue(value) {
      this.genreValue = value
    }
    
  }
}
</script>

<style lang="scss">

*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

body {
    background: #1e2d3b;
}


</style>
