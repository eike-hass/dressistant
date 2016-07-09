<template>
  <div class="butler">
    <svg class="icon"><use xlink:href="#lnr-store"></use></svg>
      <div class="count">2</div>
  </div>
</template>

<script>

export default {
  props: [
    'price',
  ],
  data() {
    return {
    };
  },
};
</script>

<style scoped>
  .butler{
    position: relative;
    width: 50px;
    height: 50px;
  }
  .butler .count{
    position: absolute;
    top: -5px;
    right: -5px;
    background: white;
    border: 1px solid black;
    border-radius: 50%;
    display: inline-block;
    width: 20px;
    height: 20px;
    text-align: center;
  }
  .icon{
    color: black;
    font-size: 50px;
    display: inline-block;
    fill: currentColor;
    width: 1em;
    height: 1em;
  }
</style>
