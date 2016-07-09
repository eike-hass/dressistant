<template>
  <div class="sizes">
    <button
      v-for="size in sizes"
      class="size"
      v-on:click="select(size)"
      v-bind:class="{ 'selected':selected === size }"
    >
      {{size}}
    </button>
  </div>
</template>

<script>

export default {
  props: [
    'sizes',
    'setActive',
    'selected',
  ],
  data() {
    return {
    };
  },
  methods: {
    select(size) {
      this.selected = size;
      this.setActive();
    },
  },

};
</script>

<style scoped>
  .sizes{
    display: flex;
  }
  .size{
    border: 1px solid gray;
    text-transform: uppercase;
    padding: 5px;
    margin-right: 5px;
    flex-grow: 1;
    height: 30px;
    background: transparent;
  }
  .selected{
    border-color: black;
  }
</style>
