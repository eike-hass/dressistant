<template>
  <div id="app">
    <header>
      <img id="logo" src="/static/Logo_dressistant.png">
      <butler :items="selectedProducts"></butler>
    </header>
    <overlay v-if="activeProduct" :product="activeProduct"></overlay>
    <main>
      <inventory :items.sync="inventoryItems"></inventory>
    </main>
    <footer>
      <suggestions :items="suggestedItems"></suggestions>
      <img src="/static/Banner.jpg">
    </footer>
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
      inventoryItems: [productMock[0], productMock[1], productMock[2]],
      activeProduct: null,
      selectedProducts: [],
    };
  },
  computed: {
    suggestedItems() {
      const items = productMock.filter((item) => {
        let matches = 0;
        this.inventoryItems.forEach((inventoryItem) => {
          const isRelated = inventoryItem.relatedProducts.indexOf(item.id) !== -1;
          const isLiked = inventoryItem.likeStatus === 'liked' &&
            inventoryItem.relatedProductsLiked.indexOf(item.id) !== -1;
          if (isRelated || isLiked) {
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
    addToList(product) {
      this.selectedProducts.push(product);
    },
  },
};
</script>
<style>
html {
  height: 100%;
}

body {
  height: calc(100% - 90px);
  margin: 90px 0 0 0;
  font-family: 'Montserrat', sans-serif;
}
header{
  position: fixed;
  height: 90px;
  top: 0;
  left: 0;
  box-sizing: border-box;
  padding-left: 20px;
  padding-right: 20px;
  width: 100%;
  background: white;
  display: flex;
  align-items: center;
  justify-content: space-between;
  z-index: 5;
  background: #333333;
  color: white;
}
header #logo{
  width: 200px;
}
main{
  padding-left: 100px;
  padding-right: 100px;
  overflow: auto;
}
img{
  max-width: 100%;
}

#app {
  color: #333333;
  display: flex;
  flex-direction: column;
  height: 100%;
}

#app main {
  flex-grow: 1;
}
</style>
