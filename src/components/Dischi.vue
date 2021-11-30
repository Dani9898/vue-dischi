<template>
  <div id="container">

    <Disco v-for="disco, i in filteredListaDischi" :key="i" :details="disco" />

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
  props: {
      genreToSearch: String
  },

  data(){
      return {
          apiURL: "https://flynn.boolean.careers/exercises/api/array/music",
          listaDischi: [],
          listaGeneri: []
      }
  },

  created(){
      this.getDischi()
  },
  
  computed: {
      filteredListaDischi() {
          if (this.genreToSearch === "") {
              return this.listaDischi
          }

          return this.listaDischi.filter(
              (item) => item.genre === this.genreToSearch
          )
      }
  },


  methods:{
      getDischi(){
        axios
        .get(this.apiURL)
        .then((result) => {

            this.listaDischi = result.data.response;

            this.listaDischi.forEach((disco) => {
                if (!this.listaGeneri.includes(disco.genre)) {
                    this.listaGeneri.push(disco.genre)
                }
            });

            this.$emit("generiList", this.listaGeneri);

        })        
      },
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
