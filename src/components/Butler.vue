<template>
  <div class="butler">
    <button v-if="items.length" v-on:click="order">
      Besorgs mir
    </button>
    <svg class="icon"><use xlink:href="#lnr-store"></use></svg>
      <div class="count">{{items.length}}</div>
  </div>
  <div v-show="showOrdered" class="overlay">
    <span>Deine Artikel sind auf dem Weg zu dir!</span>
  </div>
</template>

<script>

export default {
  props: [
    'items',
  ],
  data() {
    return {
      showOrdered: false,
    };
  },
  methods: {
    order() {
      this.showOrdered = true;
    },
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
    font-size: 20px;
    padding-top:5px;
    padding-bottom: 5px;
    margin-right: 10px;
    font-weight: bold;
    color: white;
  }
  .overlay{
    position: fixed;
    background: black;
    width: 100%;
    height: 100%;
    left:0;
    top: 0;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .overlay span{
    font-size: 40px;
  }
</style>
