<template>
  <div class="shopping-box">
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
export default {
  name: "ShoppingCart",
  data() {
    return {
      msg: "一个用Vue构建的购物车Demo"
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
h1,
h2 {
  font-weight: normal;
}
</style>
