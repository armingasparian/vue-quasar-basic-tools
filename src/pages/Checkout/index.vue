<template>
  <q-page class="checkout">
    <FormVeeValidate class="row no-wrap">
      <div class="checkout__item-cards">
        <checkout-card/>
      </div>
      <div class="checkout__item-others">
        <order-card displayType="flex" v-if="widthMoreThan768"/>
        <safe-checkout-card/>
        <ultimate-jewelery-card v-if="widthMoreThan769"/>
        <payment-method-card/>
      </div>
    </FormVeeValidate>
  </q-page>
</template>

<script>
import CheckoutCard from "src/components/CheckoutCard";
import OrderCard from "src/components/OrderCard";
import SafeCheckoutCard from "src/components/SafeCheckoutCard";
import UltimateJeweleryCard from "src/components/UltimateJeweleryCard";
import PaymentMethodCard from "src/components/PaymentMethodCard";
import {Form as FormVeeValidate} from 'vee-validate'
import {defineComponent} from "vue";
import {useWindowSize} from 'vue-window-size';

export default defineComponent({
  components: {
    CheckoutCard,
    OrderCard,
    SafeCheckoutCard,
    UltimateJeweleryCard,
    PaymentMethodCard,
    FormVeeValidate,
  },
  name: "CheckoutIndex",
  props: {
    displayType: {
      type: String,
      required: true
    },
  },
  setup() {
    const {width} = useWindowSize();
    return {
      windowWidth: width,
    };
  },
  data() {
    return {}
  },
  computed: {
    widthMoreThan769() {
      return this.windowWidth > 769
    },
    widthMoreThan768() {
      return this.windowWidth > 768
    },
  },
});
</script>
