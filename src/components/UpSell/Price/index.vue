<template>
  <q-card flat class="upSell__PriceSection">
    <div class="upSell__price">
      <span>Price:</span>
      <p class="price">${{this.price}}</p>
      <p class="percent">-80%</p>
    </div>
    <div class="upSell__quantity border-16">
      <span>Quantity:</span>
      <p @click="decreasePrice">-</p>
      <span><b>{{ this.productCount }}</b></span>
      <p @click="increasePrice">+</p>
    </div>
  </q-card>
</template>

<script>
import {defineComponent} from "vue";

export default defineComponent({
  name: "UpsellPriceSection",
  data() {
    return {
      productCount: 1,
      defaultPrice: 50,
      price: 50,
    }
  },
  methods: {
    decreasePrice() {
      this.productCount--;
      this.price = this.price - this.defaultPrice;
      if(this.price <= 0 && this.productCount <= 0) {
        this.price = 0;
        this.productCount = 0;
      }
    },
    increasePrice() {
      this.productCount++;
      this.price = this.defaultPrice * this.productCount;
      if(this.price <= 0 && this.productCount <= 0) {
        this.price = 0;
        this.productCount = 0;
      }
    }
  }
});
</script>
