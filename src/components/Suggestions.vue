<template>
  <div>
    <h1>Suggestions</h1>
    <div class="product" v-for="product in items">
      <product :product="product" layout="teaser"></product>
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
  .product{
    width: 33%;
    display: inline-block;
    box-sizing: border-box;
    padding-left:10px;
    padding-right:10px;
    vertical-align: top;
  }
</style>
