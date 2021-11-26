<template>
  <div class="container">
   
  </div>
</template>

<script>

import axios from "axios"

export default {
  name: 'Dischi',
  data(){
      return {
          apiURL: "https://flynn.boolean.careers/exercises/api/array/music",
          listaDischi = []
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
            this.listaDischi = result.data;
        })        
      }

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
