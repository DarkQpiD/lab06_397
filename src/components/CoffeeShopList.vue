<template>
  <div>
    <h2>ร้านกาแฟ</h2>
    <div class="coffee-shop-grid">
      <div v-for="coffeeShop in coffeeShops" :key="coffeeShop.id" class="coffee-shop-item">
        <div class="coffee-shop-info" @click="selectCoffeeShop(coffeeShop)">
          <img :src="coffeeShop.image" alt="ร้านกาแฟ" />
          <p>{{ coffeeShop.name }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    coffeeShops: Array,
  },
  methods: {
    selectCoffeeShop(coffeeShop) {
      if (coffeeShop.available) {
        this.$emit('reserve', { coffeeShopName: coffeeShop.name });
        this.$parent.selectedCoffeeShop = coffeeShop;
      }
    },
  },
};
</script>

<style scoped>
.coffee-shop-grid {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  
}

.coffee-shop-item {
  flex-basis: calc(33.33% - 7rem); 
  margin: 1rem; 
  box-sizing: border-box;
}

ul {
  list-style: none;
  padding: 0;
}

li {
  margin-bottom: 1rem;
  cursor: pointer;
}

.coffee-shop-info {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
}

.coffee-shop-info img {
  width: 300px;
  height: 300px;
  margin-bottom: 0.5rem;
}
</style>
