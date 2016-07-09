<template>
  <div class="butler">
    <button v-if="items.length">
      Besorgs mir
    </button>
    <svg class="icon"><use xlink:href="#lnr-store"></use></svg>
      <div class="count">{{items.length}}</div>
  </div>
</template>

<script>

export default {
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
  .butler{
    position: relative;
    display: flex;
    align-items: center;
  }
  .butler .count{
    position: absolute;
    top: -5px;
    right: -5px;
    background: #333333;
    border: 2px solid white;
    border-radius: 50%;
    display: inline-block;
    width: 20px;
    height: 20px;
    text-align: center;
  }
  .icon{
    color: white;
    font-size: 50px;
    display: inline-block;
    fill: currentColor;
    width: 1em;
    height: 1em;
  }
  button {
    background: transparent;
    text-transform: uppercase;
    border: 2px solid white;
    height: 30px;
    margin-right: 10px;
    font-weight: bold;
    color: white;
  }
</style>
