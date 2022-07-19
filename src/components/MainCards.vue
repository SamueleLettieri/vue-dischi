<template>
  <div class="p-4 ms_cards mx-3 mt-4">
    <img class="ms_img" :src="card.poster" alt="">
    <div class="text-center mt-3">
      <h3>{{card.title}}</h3>
      <h5 class="ms_t-g">{{card.author}}</h5>
      <div class="ms_t-g">{{card.year}}</div>
    </div>
  </div>
</template>

<script>
export default {
  props:["card"]
}
</script>

<style lang="scss" scoped>
.ms_cards{
  width: calc((100% / 5) - 2rem);
  background-color: rgb(50, 50, 61);
}

.ms_img{
  width: 100%;
}

h3{
  margin-bottom: 20px;
  color: white;
}

.ms_t-g{
  color: rgb(141, 141, 141);
}



</style>