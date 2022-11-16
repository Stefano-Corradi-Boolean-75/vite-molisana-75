<script>
export default {
  name: 'ProductCard',
  props:{
    cardImage: String,
    cardTitle: String
  }
}
</script>


<template>
  <div class="card">
    <img :src="cardImage" :alt="cardTitle">
    <h4>{{cardTitle}}</h4>
  </div>
</template>


<style lang="scss" scoped>

  @use '../style/partials/variables' as *;

  .card{
    flex-basis: 25%;
    background-color: white;
    border: 2px solid lighten($primary-color, 70%);
    min-height: 300px;
    padding: 15px;
    text-align: center;
  }
</style>