<template>
  <div class="product-card">
    <img src="https://i.ibb.co/GkSghgQ/Rectangle-31.png" alt="" />
    <div class="product-card__content">
      <h3>{{ item.header }}</h3>
      <p>
        {{ item.body }}
      </p>
      <span>{{ item.price }} руб.</span>
    </div>
    <div class="product-card__delete" v-on:click="removeElement(item)">
      <img src="@/static/img/delete.svg" alt="" />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    item: {
      type: Object,
      required: true,
    },
  },
  methods: {
    removeElement: function (item) {
      // this.items.delete(item);
      this.$emit("removeElement", item);
    },
  },
};
</script>

<style lang="scss">
.product-card {
  position: relative;
  margin-right: 16px;
  margin-bottom: 16px;
  width: 332px;
  background: #fffefb;
  box-shadow: 0px 20px 30px rgba(0, 0, 0, 0.04),
    0px 6px 10px rgba(0, 0, 0, 0.02);
  border-radius: 4px;
  &__content {
    padding: 16px;
    h3 {
      font-size: 20px;
      margin-bottom: 16px;
    }
    p {
      margin-bottom: 32px;
    }
    span {
      font-size: 24px;
      font-weight: 600;
    }
  }
  &__delete {
    opacity: 0;
    position: absolute;
    top: -8px;
    right: -8px;
    width: 32px;
    height: 32px;
    background: #ff8484;
    box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1);
    border-radius: 10px;
    cursor: pointer;
    transition: opacity 0.3s;
    img {
      position: absolute;
      top: 50%;
      left: 50%;
      margin-right: -50%;
      transform: translate(-50%, -50%);
    }
  }
  &:hover .product-card__delete {
    opacity: 1;
    transition: opacity 0.3s;
  }
}
</style>
