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
    border-radius: 5px;
    text-transform: uppercase;
    padding: 5px;
    flex-grow: 1;
  }
</style>
