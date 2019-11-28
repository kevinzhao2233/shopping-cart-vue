<template>
  <div class="shoping">
    <div class="card">
      <div class="select-box">
        <div class="radio" v-on:click="$emit('toggle-select')">
          <div v-bind:class="shopping.isSelect? 'noSelect isSelect': 'noSelect'"></div>
        </div>
      </div>
      <div class="img-box"></div>
      <div class="info-box">
        <div class="tit-box">
          <h3>{{ shopping.title }}</h3>
        </div>
        <span class="specify">{{ shopping.specify }}</span>
        <div class="bottom-box">
          <span class="price">￥{{ shopping.price }}</span>
          <div class="count-box">
            <div v-on:click="$emit('decrease-count')" class="decrease"></div>
            <div class="count">
              <input v-model.number:value="shopping.count" type="number" />
            </div>
            <div v-on:click="$emit('increase-count')" class="increase"></div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Shopping",
  props: {
    shopping: {
      type: Object,
      required: true
    }
  },
  data() {
    return {};
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
.card {
  display: flex;
  flex-direction: row;
  margin: 0.5rem 0;
  width: 100%;
  min-height: 8.75rem;
  overflow: hidden;
  border-bottom: 0.0625rem solid $m4;

  .select-box {
    display: flex;
    align-items: center;
    width: 1.25rem;
    height: 8rem;
    .radio {
      display: flex;
      justify-content: center;
      align-items: center;
      width: 1.25rem;
      height: 1.25rem;
      border-radius: 50%;
      border: 0.0625rem solid $m3;
      cursor: pointer;
      .noSelect {
        width: 0.75rem;
        height: 0.75rem;
        background-color: $m4;
        border-radius: 50%;
      }
      .isSelect {
        background-color: $m2;
      }
    }
  }

  .img-box {
    flex: 0 0 6rem;
    margin: 0.75rem 0 0 0.5rem;
    height: 6rem;
    background-color: $m5;
    border-radius: 0.625rem;
  }

  .info-box {
    flex: 1;
    margin: 0.75rem 0 0.75rem 0.5rem;

    .tit-box {
      height: 3rem;
      overflow: hidden;
      h3 {
        width: 100%;
        font-size: 1.125rem;
        text-overflow: ellipsis;
        overflow: hidden;
        display: -webkit-box;
        -webkit-line-clamp: 2;
        -webkit-box-orient: vertical;
      }
    }

    .specify {
      margin: 0.625rem 0;
      font-size: 0.75rem;
      color: $m2;
      line-height: 1.5rem;
    }

    .bottom-box {
      display: flex;
      justify-content: space-between;
      align-items: center;

      .price {
        font-weight: 600;
        color: $m1;
      }

      .count-box {
        display: flex;
        width: 8rem;
        height: 2rem;
        border-radius: 1rem;
        border: 0.0625rem solid $m3;

        .decrease {
          flex: 1;
        }

        .count {
          flex: 1;
          border-left: 0.0625rem solid $m3;
          border-right: 0.0625rem solid $m3;

          input {
            width: 100%;
            height: 100%;
            border: none;
            background-color: transparent;
            text-align: center;
            font-weight: 600;
          }
        }

        .increase {
          flex: 1;
        }
      }
    }
  }
}
</style>
