<template>
   <div>
    <div v-if="layout == 'compact'" class="compact">
      <div class="like">
        <like-dislike :status.sync="product.likeStatus"></like-dislike>
      </div>
      <div class="left">
        <images :images="product.images" :set-active="setActive"></images>
      </div>
      <div class="right">
        <h2>{{product.title}}</h2>
        <color-picker :colors="product.colors" :set-active="setActive"></color-picker>
        <size-picker :sizes="product.sizes" :set-active="setActive"></size-pick>
        <price :price="product.price"></price>
      </div>
    </div>
    <div v-if="layout == 'teaser'" class="teaser" v-on:click="setActive">
      <images :images="product.images"></images>
      <h2>{{product.title}}</h2>
      <price :price="product.price"></price>
    </div>
    <div v-if="layout == 'detail'" class="detail">
      <div class="left">
        <images :images="product.images"></images>
        <button>Brings mir</button>
      </div>
      <div class="right">
        <h2>{{product.title}}</h2>
        <p>{{product.description}}</p>
        <color-picker :colors="product.colors"></color-picker>
        <price :price="product.price"></price>
        <size-picker :sizes="product.sizes"></size-pick>
      </div>
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
  .compact .like{
    margin-right: 20px;
  }
  .compact .left{
    margin-right: 20px;
  }
  .detail{
    display: flex;
  }
  .detail .left{
    margin-right: 20px;
  }
</style>
