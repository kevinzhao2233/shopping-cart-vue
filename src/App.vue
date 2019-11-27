<template>
  <div id="app">
    <Header/>
    <ShoppingCart/>
  </div>
</template>

<script>
import ShoppingCart from './components/ShoppingCart'
import Header from './components/Header'

export default {
  name: 'App',
  components: {
    ShoppingCart,
    Header
  }
}
</script>

<style>
#app {
  margin: 2rem auto;
  width: 30rem;
  height: 56rem;
  border: 0.25rem solid #f1f2f6;
  border-radius: 2rem;
  overflow: hidden;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
