<template>
  <q-page class="thankYou">
    <div class="row no-wrap">
      <div class="thankYou__item-card">
        <thank-you-card />
      </div>
      <div class="thankYou__item-orders">
        <order-card displayType="none" v-if="widthMoreThan768"/>
        <safe-checkout-card/>
      </div>
    </div>
  </q-page>
</template>
<script>
import {defineComponent} from "vue";
import OrderCard from "components/OrderCard";
import SafeCheckoutCard from "components/SafeCheckoutCard";
import ThankYouCard from "components/ThankYouCard";
import { useWindowSize } from 'vue-window-size';

export default defineComponent({
  name: "ThankYouIndex",
  components: {ThankYouCard, SafeCheckoutCard, OrderCard},
  setup() {
    const { width } = useWindowSize();
    return {
      windowWidth: width,
    };
  },
  data() {
    return {
    }
  },
  computed: {
    widthMoreThan768() {
      return this.windowWidth > 768
    },
  }
});
</script>
