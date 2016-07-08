<template>
   <div>
    <div v-if="layout == 'compact'" class="compact">
      <div class="left">
        <like-dislike :status.sync="product.likeStatus"></like-dislike>
        <images :images="product.images"></images>
      </div>
      <div class="right">
        <h2>{{product.title}}</h2>
        <color-picker :colors="product.colors"></color-picker>
        <size-picker :sizes="product.sizes" :set-active="setActive"></size-pick>
        <price :price="product.price"></price>
      </div>
    </div>
    <div v-if="layout == 'teaser'" class="teaser">
      <images :images="product.images"></images>
      <h2>{{product.title}}</h2>
      <price :price="product.price"></price>
    </div>
    <div v-if="layout == 'detail'" class="detail">
      <images :images="product.images"></images>
      <h2>{{product.title}}</h2>
      <p>{{product.description}}</p>
      <color-picker :colors="product.colors"></color-picker>
      <size-picker :sizes="product.sizes"></size-pick>
      <price :price="product.price"></price>
    </div>
  </div>
</template>

<script>
import Images from './Images';
import ColorPicker from './ColorPicker';
import SizePicker from './SizePicker';
import Price from './Price';
import LikeDislike from './LikeDislike';

export default {
  components: {
    Images,
    ColorPicker,
    SizePicker,
    Price,
    LikeDislike,
  },
  props: [
    'product',
    'layout',
  ],
  data() {
    return {};
  },
  methods: {
    setActive() {
      console.log('click');
      this.$dispatch('setActiveProduct', this.product);
    },
  },
};
</script>

<style scoped>
  .compact{
    display: flex;
    text-align: left;
  }
  .compact .left{
    margin-right: 20px;
  }
</style>
