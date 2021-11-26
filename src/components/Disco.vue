<template>
  <div class="my-disk">

    <div class="disk-img">
      <img :src="details.poster" :alt="details.title">
    </div>

    <h2>{{details.title}}</h2>
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


<style scoped lang="scss">

.my-disk {
  width: calc(20% - 40px);
  height: 420px;
  margin: 10px 20px;
  padding: 0 15px;
  background-color: #2e3a46;
  display: flex;
  flex-flow: column;
  align-items: center;

    .disk-img {
      width: 85%;
      margin-top: 25px;

        img {
          width: 100%;
        }
    }

    h2 {
      color: white;
      font-size: 30px;
      text-align: center;
      margin: 10px 0 20px 0;
    }

    span {
      color: #808078;
      font-size: 22px;
    }
}


</style>
