<template>
  <div>
    <h3>Gefällt dir dieses Produkt?</h3>
    <button v-on:click="status = 'liked'"><svg class="icon"><use xlink:href="#lnr-heart"></use></svg></button>
    <button v-on:click="status = 'disliked'" class="dislike"><svg class="icon"><use xlink:href="#lnr-heart"></use></svg></button>
  </div>
</template>

<script>

export default {
  props: [
    'status',
  ],
  data() {
    return {
    };
  },
};
</script>

<style scoped>
  h3{
    font-size: 16px;
  }
  button{
    display: inline-block;
    backgound: transparent;
    background: none;
    border: none;
    width: 50px;
    height: 50px;
    position: relative;
  }
  button svg{
    position: relative;
    z-index: -1;
  }
  .icon{
    color: black;
    font-size: 50px;
    display: inline-block;
    fill: currentColor;
    width: 40px;
    height: 40px;
  }
  .dislike::after{
    content: '';
    width: 52px;
    height: 2px;
    background: black;
    display: block;
    top: 22px;
    left: 1px;
    transform: rotateZ(-45deg);
    position: absolute;
  }
</style>
