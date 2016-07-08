<template>
  <div class="sizes">
    <button v-for="size in sizes" class="size" v-on:click="setActive">
      {{size}}
    </button>
  </div>
</template>

<script>

export default {
  props: [
    'sizes',
    'setActive',
  ],
  data() {
    return {
    };
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
</style>
