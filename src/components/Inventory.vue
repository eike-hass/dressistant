<template>
  <div class="inventory">
    <h1>Inventory</h1>
    <div class="product" v-for="product in items">
      <product :product.sync="product" layout="compact"></product>
    </div>
  </div>
</template>

<script>
  import Product from './Product';
  export default {
    components: {
      Product,
    },
    props: [
      'items',
    ],
    data() {
      return {
      };
    },
  };
</script>

<style scoped>
  .inventory{

  }
  h1{
    text-align: center;
  }
  .product{
    margin-bottom: 20px;
  }
</style>
