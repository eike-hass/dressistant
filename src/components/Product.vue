<template>
   <div>
    <div v-if="layout == 'compact'" class="compact">
      <div class="left">
        <images :images="product.images[product.colors.indexOf(product.selectedColor)]" :set-active="setActive"></images>
      </div>
      <div class="right">
        <h2>{{product.title}}</h2>
        <color-picker :colors="product.colors" :selected.sync="product.selectedColor" :set-active="setActive"></color-picker>
        <size-picker :sizes="product.sizes" :selected.sync="product.selectedSize" :set-active="setActive"></size-picker>
        <like-dislike :status.sync="product.likeStatus"></like-dislike>
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
        <button v-on:click="addToList">Brings mir</button>
      </div>
      <div class="right">
        <h2>{{product.title}}</h2>
        <p>{{product.description}}</p>
        <color-picker :colors="product.colors" :selected.sync="product.selectedColor"></color-picker>
        <price :price="product.price"></price>
        <size-picker :sizes="product.sizes" :selected.sync="product.selectedSize"></size-pick>
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
    addToList() {
      this.$dispatch('addToList', this.product);
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
    width: 50%;
  }
  .compact .right{
    width: 50%;
    text-align: center;
  }
  .detail{
    display: flex;
  }
  .detail .left{
    margin-right: 20px;
    max-width: 60%;
  }
  .detail button{
    background: black;
    border: 2px solid black;
    width: 100%;
    color: white;
    height: 40px;
    text-transform: uppercase;
  }
</style>
