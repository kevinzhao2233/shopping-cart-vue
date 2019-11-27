<template>
  <div class="shopping-box">
    <div class="edit-box">
      <span class="select-all">
        <div class="radio" id="selectAll">
          <div class="isSelect"></div>
        </div>
        <span class="text">全选</span>
      </span>
      <span class="edit">编辑</span>
    </div>
    <div class="shopping-card-box">
      <Shopping />
      <Shopping />
      <Shopping />
    </div>
    <div class="footer">
      <div class="total-box">
        <span class="total">合计</span>
        <span class="price">￥3451</span>
      </div>
      <div class="submit">结算</div>
    </div>
  </div>
</template>

<script>
import Shopping from "./Shopping";

export default {
  name: "ShoppingCart",
  data() {
    return {
      msg: "一个用Vue构建的购物车Demo"
    };
  },
  components: {
    Shopping
  }
};
</script>

<style lang="scss" scoped>
$m1: #2c3340;
$m2: #646d7f;
$m3: #b1b8c8;
$m4: #e6e9f0;
$m5: #f1f2f6;
$m6: #ffffff;

.shopping-box {
  position: relative;
  height: 100%;

  .edit-box {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin: 0 auto;
    width: 95%;
    height: 3rem;
    font-size: 1rem;
    border-bottom: 0.0625rem solid $m4;

    .select-all {
      display: flex;
      align-items: center;
      .radio {
        display: flex;
        justify-content: center;
        align-items: center;
        width: 1rem;
        height: 1rem;
        border-radius: 50%;
        border: 0.0625rem solid $m3;
        cursor: pointer;

        .isSelect {
          width: 0.625rem;
          height: 0.625rem;
          background-color: $m3;
          border-radius: 50%;
        }
      }
      .text {
        margin: 0 0 0 0.5rem;
        line-height: 1rem;
      }
    }

    .edit {
      font-weight: 600;
    }
  }

  .shopping-card-box {
    margin: 0 auto;
    width: 95%;
  }

  .footer {
    position: absolute;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 5%;
    bottom: 3rem;
    width: 100%;
    height: 4rem;
    background-color: $m5;
    box-shadow: 0 .5rem 1.25rem $m3;

    .total-box {
      font-size: 1.25rem;
      font-weight: 600;
    }

    .submit {
      display: flex;
      justify-content: center;
      align-items: center;
      width: 7rem;
      height: 2.5rem;
      background-color: $m2;
      border-radius: 2rem;
      font-size: 1.125rem;
      color: $m6;
      font-weight: bold;
      line-height: 2rem;
    }
  }
}
</style>
