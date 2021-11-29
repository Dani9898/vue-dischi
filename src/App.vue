<template>
  <div id="app">

    <Header/>

    <Dischi/>

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
