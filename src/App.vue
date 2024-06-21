<template>
  <div>
    <FriendsComp></FriendsComp>
    <ProductsComp></ProductsComp>
  </div>
</template>

<script>
import FriendsComp from './components/FriendsComp.vue';
import ProductsComp from './components/ProductsComp.vue';


export default {
  name: 'App',
  components: {
    FriendsComp,
    ProductsComp
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
