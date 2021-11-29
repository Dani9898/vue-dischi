<template>
  <div id="container">
   
      <FilterDischi @search="filterDisks" :details="listaDischi" />
      <Disco v-for="disco, i in filteredListaDischi" :key="i" :details="disco" />

  </div>
</template>

<script>

import axios from "axios"
import Disco from '@/components/Disco.vue'
import FilterDischi from '@/components/FilterDischi.vue'


export default {
  name: 'Dischi',
  components: {
      Disco,
      FilterDischi
  },
  data(){
      return {
          apiURL: "https://flynn.boolean.careers/exercises/api/array/music",
          listaDischi: [],
          optionValue: ""
      }
  },

  created(){
      this.getDischi()
  },
  
  computed: {
      filteredListaDischi() {
          if (this.optionValue === "") {
              return this.listaDischi
          }

          return this.listaDischi.filter((item) => {
              return item.genre.toLowerCase().includes(this.optionValue.toLowerCase())
          })
      }
  },


  methods:{
      getDischi(){
        axios
        .get(this.apiURL)
        .then((result) => {
            this.listaDischi = result.data.response;
        })        
      },

      filterDisks(value) {
          this.optionValue = value
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
#container {
    width: 70%;
    margin: auto;
    padding: 60px 0;
    background-color: #1e2d3b;
    display: flex;
    flex-wrap: wrap;
}
</style>
