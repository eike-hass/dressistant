<template>
  <div>
    <div
      v-for="color in colors"
      class="color"
      v-bind:style="{ background: color }"
      v-bind:class="{ 'selected':selected === color }"
      v-on:click="select(color)"
    ></div>
  </div>
</template>

<script>

export default {
  props: [
    'colors',
    'setActive',
    'selected',
  ],
  data() {
    return {
    };
  },
  methods: {
    select(color) {
      this.selected = color;
      this.setActive();
    },
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
  .selected{
    border-color: black;
  }
</style>
