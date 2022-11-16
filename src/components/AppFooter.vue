<script>

import links from '../data/menu';

export default {
  name: 'AppFooter',
  data(){
    return{
      footerImg: 'footer.jpg',
      links
    }
  },
  methods:{
    getImagePath(imageName){
      return new URL(`../assets/img/${imageName}`, import.meta.url).href
    }
  }
}
</script>

<template>
  <footer>

    <div class="cols container">
      <div>
        <img src="/logo-molisana.png" alt="Logo La Molisana">
      </div>
      <div class="links">
        <h4>Menu</h4>
        <nav>
          <ul>
            <li v-for="(link, index) in links" :key="index"><a :href="link.href">{{link.text}}</a></li>
          </ul>
        </nav>
      </div>
      <div class="links">
        <h4>Pastificio</h4>
        <nav>
          <ul>
            <li><a href="#">Il Pastificio</a></li>
            <li><a href="#">Grano</a></li>
            <li><a href="#">Filiera</a></li>
            <li><a href="#">100 anni di pasta</a></li>
            <li><a href="#">Sartoria della pasta</a></li>
          </ul>
        </nav>
      </div>
      <div class="links">
        <h4>Prodotti</h4>
        <nav>
          <ul>
            <li><a href="#">Le classiche</a></li>
            <li><a href="#">Le Integrali</a></li>
            <li><a href="#">Le Speciali</a></li>
            <li><a href="#">Le Biologiche</a></li>
            <li><a href="#">Le Gluten-free</a></li>
          </ul>
        </nav>
      </div>
    </div>

    <!-- importazione statica dell'immagine -->
    <!-- <img src="../assets/img/footer.jpg" alt="Montagne"> -->

    <!-- importazione dinamica dell'immagine -->
    <img :src="getImagePath(footerImg)" alt="Montagne">

  </footer>
</template>


<style lang="scss" scoped>
@use '../style/partials/variables' as *;
@use '../style/partials/mixin' as *;

footer{
  padding: 30px 0;
  .cols{
    display: flex;
    .links{
      margin-left: 150px;
      h4{
        text-transform: uppercase;
        font-size: 1.2rem;
        margin-bottom: 20px;
      }
      ul{
        list-style: none;
        a{
          display: inline-block;
          color: black;
          text-decoration: none;
          font-size: .85rem;
          margin-bottom: 5px;
          &:hover{
            color: $primary-color;
          }
        }
      }
    }
  }
}

</style>