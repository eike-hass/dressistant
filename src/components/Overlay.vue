<template>
  <div class="backdrop" v-on:click="close">
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
  methods: {
    close() {
      this.$dispatch('setActiveProduct', null);
    },
  },
};
</script>

<style scoped>
  .backdrop{
    position: fixed;
    width: 100%;
    height: calc(100% - 90px);
    left: 0;
    top: 90px;
    background: rgba(0,0,0,.95);
    display: flex;
    justify-content: center;
    align-items: center;
    z-index:4;
  }
  .content{
    background: white;
    padding: 20px;
    height: 100%;
  }
</style>
