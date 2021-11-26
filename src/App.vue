<template>
  <div id="app">
    <Dischi/>
  </div>
</template>

<script>
import Dischi from './components/Dischi.vue'

export default {
  name: 'App',
  components: {
    Dischi
  }
}
</script>

<style lang="scss">
#app {

  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

}
</style>
