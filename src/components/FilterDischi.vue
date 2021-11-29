<template>
  <div id="select">

      <select name="genre" v-model="thisValue" @change="$emit('search', thisValue)">
        <option value="">All</option>
        <option v-for="disco, i in details" :key="i" :value="disco.genre" >{{disco.genre}}</option>
      </select>

  </div>
</template>

<script>


export default {
  name: 'FilterDischi',
  props: {
      details: Array
  },
  data(){
    return {
      thisValue: "",
    }
  }

}
</script>

<style scoped lang="scss">


</style>
