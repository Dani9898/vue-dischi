<template>
  <div class="my-disk">

    <div class="disk-img">
      <img :src="details.poster" :alt="details.title">
    </div>

    <span>{{details.title}}</span>
    <span>{{details.author}}</span>
    <span>{{details.year}}</span>
  
  </div>
</template>

<script>
export default {
  name: 'Disco',
  props: {
    details: Object
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
