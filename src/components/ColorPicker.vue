<template>
  <div>
    <div v-for="color in colors" class="color" v-bind:style="{ background: color }"></div>
  </div>
</template>

<script>

export default {
  props: [
    'colors',
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
    border-radius: 50%;
    display: inline-block;
  }
</style>
