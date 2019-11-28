<template>
  <div class="header">
    <div class="header-box">
      <span class="title">{{ tit }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "Header",
  data() {
    return {
      tit: "购物车"
    };
  }
};
</script>

<style lang="scss" scoped>
.header-box {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 2rem;
  width: 100%;
  height: 3rem;
  text-align: center;

  .title {
    font-size: 1.2rem;
    letter-spacing: 0.0625rem;
  }
}
</style>
