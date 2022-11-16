<script>

import ProductCard from './ProductCard.vue';

import products from '../data/products';

export default {
  name: 'AppMain',
  components:{
    ProductCard
  },
  data(){
    return{
      products
    }
  }
}
</script>

<template>
  <main>
    <div class="container cards">

     <ProductCard 
        v-for="(card, index) in products" 
        :key="index"
        :cardImage="card.src"
        :cardTitle="card.titolo"
       />
      
    </div>

  </main>
</template>



<style lang="scss" scoped>
  main{
    padding: 50px 0;
    background-image: url('../assets/img/bg-prods.jpg');
    min-height: 500px;
    .cards{
      display: flex;
      flex-wrap: wrap;
    }
  }
</style>