<template>

    <header>

    <select name="genre" v-model="thisValue" @change="$emit('search', thisValue)">
        <option value="">All</option>
        <option v-for="genere, i in generi" :key="i" :value="genere" >{{genere}}</option>
    </select>

    </header>

</template>

<script>
export default {
  name: 'Header',
   props: {
      generi: Array
  },
  data(){
    return {
      thisValue: "",
    }
  }
}
</script>


<style scoped lang="scss">

    header {
        background-color: #2e3a46;
        height: 70px;
    }

</style>
