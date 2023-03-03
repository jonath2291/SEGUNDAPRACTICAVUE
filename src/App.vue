<template>
<MenuNav/>
  <ProductSelect/>
  <ProductCard/>
  <FooterPage/>
</template>

<script>
import ProductSelect from './components/ProductSelect.vue';
import MenuNav from './components/MenuNav.vue';
import FooterPage from './components/FooterPage.vue';
import ProductCard from './components/ProductCard.vue';

export default {
  name: 'App',
  components: {
    ProductSelect,
    MenuNav,
    FooterPage,
    ProductCard
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
