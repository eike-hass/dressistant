<template>
  <div id="app">
    <butler></butler>
    <overlay v-if="activeProduct" :product="activeProduct"></overlay>
    <inventory :items.sync="inventoryItems"></inventory>
    <suggestions :items="suggestedItems"></suggestions>
  </div>
</template>

<script>
import Inventory from './components/Inventory';
import Suggestions from './components/Suggestions';
import Overlay from './components/Overlay';
import Butler from './components/Butler';

import productMock from './product';

export default {
  components: {
    Butler,
    Inventory,
    Suggestions,
    Overlay,
  },
  data() {
    return {
      inventoryItems: [productMock[0], productMock[1]],
      activeProduct: null,
    };
  },
  computed: {
    suggestedItems() {
      const items = productMock.filter((item) => {
        let matches = 0;
        this.inventoryItems.forEach((inventoryItem) => {
          const isRelated = inventoryItem.relatedProducts.indexOf(item.id) !== -1;
          const isNotDisliked = inventoryItem.likeStatus === 'liked';
          if (isRelated && isNotDisliked) {
            matches++;
          }
        });

        return matches;
      });

      return items;
    },
  },
  events: {
    setActiveProduct(product) {
      this.activeProduct = product;
    },
  },
};
</script>
<style>
html {
  height: 100%;
}

body {
  //display: flex;
  //align-items: center;
  //justify-content: center;
  height: 100%;
  padding-left: 20px;
  padding-right: 20px;
}

img{
  max-width: 100%;
}

#app {
  color: #2c3e50;
  font-family: Source Sans Pro, Helvetica, sans-serif;
}
</style>
