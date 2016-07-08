<template>
  <div>
    <div v-for="color in colors" class="color" v-bind:style="{ background: color }" v-on:click="setActive"></div>
  </div>
</template>

<script>

export default {
  props: [
    'colors',
    'setActive',
  ],
  data() {
    return {
    };
  },
};
</script>

<style scoped>
  .color{
    width: 30px;
    height: 30px;
    border: 1px solid gray;
    display: inline-block;
    margin-right: 5px;
  }
</style>
