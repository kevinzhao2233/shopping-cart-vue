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
  width: 100vw;
  height: 100%;
  overflow: hidden;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
