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
      <!-- <Shopping info="{{" shoppingInfo.101 }} /> -->
      <Shopping
        v-for="shopping in shoppings"
        v-bind:key="shopping.id"
        v-bind:shopping="shopping"
        v-on:decrease-count="shopping.count -= 1"
        v-on:increase-count="shopping.count += 1"
        v-on:toggle-select="shopping.isSelect = !shopping.isSelect"
      ></Shopping>
    </div>
    <div class="footer">
      <div class="total-box">
        <span class="total">合计</span>
        <span class="price">{{ calcPrice() }}</span>
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
      shoppings: [
        {
          id: 101,
          title: "A衣服，正品WOOG黑色棒球领男士羽绒服冬季加厚短款羽绒衣潮流",
          img: "",
          specify: "黑色 XXL",
          price: 788,
          count: 1,
          isSelect: false
        },
        {
          id: 102,
          title: "B衣服，GXG男装2019年冬新款复古毛衣男宽松袖针织衫毛衣羊毛衫",
          img: "",
          specify: "白色 XXXL",
          price: 799,
          count: 1,
          isSelect: true
        },
        {
          id: 103,
          title: "C衣服，GXG男装2019冬季新款韩版宽松大口袋束腿裤潮牌休闲长裤",
          img: "",
          specify: "黑色 XXXL",
          price: 599,
          count: 2,
          isSelect: true
        }
      ],
      totalPrice: 0
    };
  },
  methods: {
    calcPrice: function() {
      let tempPrice = 0;
      for (const index in this.shoppings) {
        if (this.shoppings[index].isSelect) {
          tempPrice +=
            this.shoppings[index].price * this.shoppings[index].count;
        }
      }
      this.totalPrice = tempPrice;
      return this.totalPrice;
    }
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
  height: (100) rem;
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
        width: 1.25rem;
        height: 1.25rem;
        border-radius: 50%;
        border: 0.0625rem solid $m3;
        cursor: pointer;
        .isSelect {
          width: 0.75rem;
          height: 0.75rem;
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
    margin: 0 auto 20rem auto;
    width: 95%;
  }
  .footer {
    position: fixed;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 5%;
    width: 100%;
    height: 4rem;
    background-color: $m5;
    bottom: 0;
    box-shadow: 0 -0.2rem 1rem $m3;
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
