<template>
  <div class="container">
   
      <Disco v-for="disco, i in listaDischi" :key="i" :details="disco" />

  </div>
</template>

<script>

import axios from "axios"
import Disco from '@/components/Disco.vue'


export default {
  name: 'Dischi',
  components: {
      Disco
  },
  data(){
      return {
          apiURL: "https://flynn.boolean.careers/exercises/api/array/music",
          listaDischi: []
      }
  },

  created(){
      this.getDischi()
  },

  methods:{
      getDischi(){
        axios
        .get(this.apiURL)
        .then((result) => {
            this.listaDischi = result.data.response;
        })        
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
