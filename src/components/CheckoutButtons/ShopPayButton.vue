<template>
  <div class="shopPayButton">
    <button>
      <img :src="shopPay"/>
    </button>
  </div>
</template>

<script>
import {defineComponent} from "vue";
import shopPay from "assets/shop-pay.png";

export default defineComponent({
  name: "ShopPayButton",
  data() {
    return {
      shopPay: shopPay,
    }
  },
  setup() {
    return {};
  },
});
</script>

<style></style>
