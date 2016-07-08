<template>
  <div class="sizes">
    <div v-for="size in sizes" class="size">
      {{size}}
    </div>
  </div>
</template>

<script>

export default {
  props: [
    'sizes',
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
