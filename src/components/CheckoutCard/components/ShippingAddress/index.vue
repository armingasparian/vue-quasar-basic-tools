<template>
  <div class="shippingAddress">
    <content-title :contentTitle="contentTitle"/>
    <div class="shippingAddress__form">
      <billing-address-form/>
    </div>
  </div>
</template>

<script>
import {defineComponent} from "vue";
import ContentTitle from "components/Titles/ContentTitle.vue";
import BillingAddressForm from "components/BillingAddressForm/index.vue";

export default defineComponent({
  name: "ShippingAddress",
  components: {
    BillingAddressForm,
    ContentTitle,
  },
  data() {
    return {
      contentTitle: "Shipping address",
    }
  },
  setup() {
    return {};
  },
});
</script>

<style></style>

