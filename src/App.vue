<template>
  <div class="main">
    <Form @onSubmit="handleSubmit" />
    <List :items="items" />
  </div>
</template>

<script>
import Form from "@/components/Form";
import List from "@/components/List";

export default {
  name: "App",
  components: {
    Form,
    List,
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
    handleSubmit(item) {
      this.items.push(item);
    },
  },
};
</script>
<style lang="scss">
.main {
  display: flex;
  flex-wrap: nowrap;
}
</style>
