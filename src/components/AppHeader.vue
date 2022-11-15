<script>
export default {
  name: 'AppHeader',
  data(){
    return{
      menu:[
        {
          text: 'Home',
          href: '#',
          current: false
        },
        {
          text: 'Prodotti',
          href: '#',
          current: true
        },
        {
          text: 'Chi siamo',
          href: '#',
          current: false
        },
        {
          text: 'Contatti',
          href: '#',
          current: false
        },
      ]
    }
  }
}
</script>

<template>
  <header>
    <div class="logo">
      <!-- percorso assoluto perché l'immagine è in public -->
      <img src="/logo-molisana.png" alt="Logo La Molisana">
    </div>

    <nav>
      <ul>
        <li
          v-for="(link, index) in menu"
          :key="index"
        ><a :class="{'active': link.current}" :href="link.href">{{link.text}}</a></li>
      </ul>
    </nav>

  </header>
</template>



<style lang="scss" scoped>

@use '../style/partials/variables' as *;
@use '../style/partials/mixin' as *;

header{
  text-align: center;
  margin-bottom: 50px;
  .logo{
    margin-bottom: 50px;
  }
  ul{
    list-style: none;
    @include centerFlex('horizontal');
    a{
      text-decoration: none;
      display: inline-block;
      padding: 1rem;
      color: black;
      font-weight: 600;
      &:hover,
      &.active{
        background-color: lighten($primary-color, 65%);
      }
    }
  }
}

</style>