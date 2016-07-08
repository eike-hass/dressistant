<template>
  <div id="app">
    <overlay v-if="activeProduct" :product="activeProduct"></overlay>
    <inventory :items.sync="inventoryItems"></inventory>
    <suggestions :items="suggestedItems"></suggestions>
  </div>
</template>

<script>
import Inventory from './components/Inventory';
import Suggestions from './components/Suggestions';
import Overlay from './components/Overlay';

import productMock from './product';

export default {
  components: {
    Inventory,
    Suggestions,
    Overlay,
  },
  data() {
    return {
      inventoryItems: [productMock[0]],
      activeProduct: null,
    };
  },
  computed: {
    suggestedItems: function () { // eslint-disable-line

      const items = productMock.filter((item) => {
        let matches = 0;
        this.inventoryItems.forEach((inventoryItem) => {
          const isRelated = inventoryItem.relatedProducts.indexOf(item.id) !== -1;
          const isNotDisliked = inventoryItem.likeStatus !== 'disliked';
          if (isRelated && isNotDisliked) {
            matches++;
          }
        });

        return matches;
      });

      return items;
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
  text-align: center;
}

#app a {
  color: #42b983;
  text-decoration: none;
}

.logo {
  width: 100px;
  height: 100px
}
</style>
