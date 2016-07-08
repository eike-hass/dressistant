<template>
  <div class="backdrop">
    <div class="content">
      <product :product="product" layout="detail"></product>
    </div>
  </div>
</template>

<script>

export default {
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
    background: rgba(0,0,0,.8);
  }
</style>
