<template>
  <div>
    {{status}}
    <button v-on:click="status = 'liked'">Like</button>
    <button v-on:click="status = 'disliked'">Dislike</button>
  </div>
</template>

<script>

export default {
  props: [
    'status',
  ],
  data() {
    return {
    };
  },
};
</script>

<style scoped>

</style>
