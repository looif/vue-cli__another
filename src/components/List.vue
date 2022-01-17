<template>
  <div class="product-list">
    <Item
      v-for="item in items"
      :key="item.id"
      :item="item"
      @removeElement="removeElement(item.id)"
    />
  </div>
</template>

<script>
import Item from "@/components/Item";

export default {
  components: {
    Item,
  },
  data() {
    return {
      items: [
        {
          id: 1,
          header: "Наименование товара",
          body: "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
          price: "10 000",
        },
        {
          id: 2,
          header: "Наименование товара",
          body: "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
          price: "12 000",
        },
      ],
    };
  },
  methods: {
    removeElement: function (id) {
      console.log(id);
      const itemId = this.items.findIndex((item) => item.id == id);
      this.items = [
        ...this.items.slice(0, itemId),
        ...this.items.slice(itemId + 1),
      ];
    },
  },
};
</script>
<style lang="scss">
.product-list {
  display: flex;
  flex-wrap: wrap;
}
</style>
