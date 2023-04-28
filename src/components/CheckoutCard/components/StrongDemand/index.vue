<template>
  <div class="strongDemand">
    <p class="checkoutCard__demand">Strong demand! Complete your order before it's too late!</p>
    <p class="card-reserved">Your cart is reserved for <span>10:00 minutes</span>.</p>
    <express-checkout />
    <lifetime-warranty />
  </div>
</template>

<script>
import {defineComponent} from "vue";
import ExpressCheckout from "components/CheckoutCard/components/StrongDemand/ExpressCheckout/index.vue";
import LifetimeWarranty from "components/CheckoutCard/components/StrongDemand/LifetimeWarranty/index.vue";

export default defineComponent({
  name: "StrongDemand",
  components: {
    LifetimeWarranty,
    ExpressCheckout
  },
  data() {
  },
  setup() {
    return {};
  },
});
</script>

<style></style>

