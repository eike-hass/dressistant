<template>
  <div class="sizes">
    <h3>In den folgenden Größen verfügbar:</h3>
    <div>
      <button
        v-for="size in sizes"
        class="size"
        v-on:click="select(size)"
        v-bind:class="{ 'selected':selected === size }"
      >
        {{size}}
      </button>
    </div>
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

  }
  h3{
    font-size: 16px;
  }
  .size{
    border: 1px solid gray;
    text-transform: uppercase;
    padding: 5px;
    margin-right: 5px;
    flex-grow: 1;
    height: 30px;
    background: transparent;
    border-radius: 50%;
  }
  .selected{
    background: black;
    color: white;
  }
</style>
