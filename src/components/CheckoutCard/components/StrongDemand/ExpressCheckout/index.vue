<template>
  <div class="expressCheckout border-16">
    <paragraph-title :paragraphTitle="paragraphTitle"/>
    <div class="expressCheckout__buttons">
      <shop-pay-button />
      <pay-pall-button />
      <google-pay-button />
    </div>
  </div>
</template>

<script>
import {defineComponent} from "vue";
import ShopPayButton from "components/CheckoutButtons/ShopPayButton.vue";
import GooglePayButton from "components/CheckoutButtons/GooglePayButton.vue";
import PayPallButton from "components/CheckoutButtons/PayPalButton.vue";
import ParagraphTitle from "components/Titles/ParagraphTitle.vue";

export default defineComponent({
  name: "ExpressCheckout",
  components: {
    ParagraphTitle,
    GooglePayButton,
    PayPallButton,
    ShopPayButton,
  },
  data() {
    return {
      paragraphTitle: "Express Checkout",
    }
  },
  setup() {
    return {};
  },
});
</script>

<style></style>

