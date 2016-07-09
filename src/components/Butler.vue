<template>
  <div class="butler">
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
    position: fixed;
    right: 20px;
    top: 20px;
    width: 50px;
    height: 50px;
    border: 2px solid black;
    border-radius: 50%;
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
</style>
