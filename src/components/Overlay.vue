<template>
  <div class="backdrop">
    <div class="content">
      <product :product="product" layout="detail"></product>
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
    'product',
  ],
  data() {
    return {
    };
  },
};
</script>

<style scoped>
  .backdrop{
    position: fixed;
    width: 100%;
    height: 100%;
    left: 0;
    top: 0;
    background: rgba(0,0,0,.95);
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .content{
    background: white;
  }
</style>
