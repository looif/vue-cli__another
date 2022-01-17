<template>
  <form class="add-product" @submit.prevent="onSubmit">
    <div class="add-product__name">
      <label for="name">Наименование товара<span class="red">*</span></label>
      <input
        v-model="header"
        type="text"
        id="name"
        placeholder="Введите наименование товара"
      />
    </div>
    <div class="add-product__name">
      <label for="name">Описание товара</label>
      <textarea
        v-model="body"
        rows="5"
        type="text"
        id="name"
        placeholder="Введите описание товара"
      />
    </div>
    <div class="add-product__name">
      <label for="name"
        >Ссылка на изображение товара<span class="red">*</span></label
      >
      <input type="text" id="name" placeholder="Введите ссылку" />
    </div>
    <div class="add-product__name">
      <label for="name">Цена товара<span class="red">*</span></label>
      <input
        v-model="price"
        type="number"
        id="name"
        placeholder="Введите цену"
        max="1000000"
      />
    </div>
    <button class="add-product__button" type="submit">Добавить товар</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      header: "",
      body: "",
      price: "",
    };
  },
  methods: {
    onSubmit() {
      this.$emit("onSubmit", {
        id: Math.round(Math.random() * 30),
        header: this.header,
        body: this.body,
        price: this.price,
      });

      this.header = "";
      this.body = "";
      this.price = "";
    },
  },
};
</script>

<style lang="scss">
.add-product {
  text-align: left;
  width: 332px;
  background: #fffefb;
  box-shadow: 0px 20px 30px rgba(0, 0, 0, 0.04),
    0px 6px 10px rgba(0, 0, 0, 0.02);
  border-radius: 4px;
  margin-right: 16px;
  padding: 24px;
  &__name {
    display: inline-block;
    width: 100%;
    margin-bottom: 16px;
    input,
    label {
      display: block;
    }
    .red {
      font-size: 18px;
      color: #ff8484;
    }
  }
  &__button:invalid:required {
    width: 100%;
    padding: 12px 20px;
    font-size: 16px;
    font-weight: 600;
    color: #b4b4b4;
    border: none;
    background: #eeeeee;
    border-radius: 10px;
    cursor: pointer;
  }
  &__button:valid {
    width: 100%;
    padding: 12px 20px;
    font-size: 16px;
    font-weight: 600;
    color: #ffffff;
    border: none;
    background: #7bae73;
    box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1);
    border-radius: 10px;
    cursor: pointer;
  }
}
</style>
