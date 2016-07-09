<template>
  <div v-on:click="setActive">
    <img :src="images[0]">
  </div>
</template>

<script>
export default {
  props: [
    'images',
  ],
  data() {
    return {
    };
  },
};
</script>

<style scoped>

</style>
