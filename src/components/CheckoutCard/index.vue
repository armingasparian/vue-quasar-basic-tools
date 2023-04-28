<template>
  <q-card flat class="checkoutCard">
    <page-title :pageTitle="pageTitle"/>
    <order-card-mobile
        v-if="widthLessThan769"
        :displayType="displayType"
        @summary="mySummary = $event"
    />
    <ultimate-jewelery-card v-if="ultimateJewelery"/>
    <strong-demand/>
    <contact-information/>
    <shipping-address/>
    <shipping-method/>
    <billing-address/>
  </q-card>
</template>

<script>
import {defineComponent} from "vue";
import { useWindowSize } from 'vue-window-size';
import PageTitle from "components/Titles/PageTitle.vue";
import ContactInformation from "components/CheckoutCard/components/ContactInformation/ContactInformation.vue";
import StrongDemand from "components/CheckoutCard/components/StrongDemand/index.vue";
import ShippingAddress from "components/CheckoutCard/components/ShippingAddress/index.vue";
import ShippingMethod from "components/CheckoutCard/components/ShippingMethod/index.vue";
import BillingAddress from "components/CheckoutCard/components/BillingAddress/index.vue";
import OrderCardMobile from "components/OrderCardMobile/index.vue";
import UltimateJeweleryCard from "components/UltimateJeweleryCard/index.vue";

export default defineComponent({
  name: "CheckoutCard",
  components: {
    UltimateJeweleryCard,
    OrderCardMobile,
    BillingAddress,
    ShippingMethod,
    ShippingAddress,
    StrongDemand,
    PageTitle,
    ContactInformation,
  },
  setup() {
    const { width } = useWindowSize();
    return {
      windowWidth: width,
    };
  },
  props: {
    displayType: {
      type: String,
      default: 'flex',
    },
  },
  data() {
    return {
      pageTitle: "Checkout",
      mySummary: false,
    }
  },
  computed: {
    widthLessThan769() {
      return this.windowWidth < 769
    },
    ultimateJewelery() {
      return this.windowWidth < 769 && this.mySummary === true
    },
  },
});
</script>

<style></style>
