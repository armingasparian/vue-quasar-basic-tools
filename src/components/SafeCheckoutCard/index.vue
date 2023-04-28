<template>
  <q-card flat class="safeCheckoutCard">
    <div class="safeCheckoutCard__content">
      <div>
        <img :src="lockImage"/>
        <p>Secure SSL Encryption & Guaranteed Safe Checkout</p>
      </div>
      <div>
        <div><img :src="cardMaster"/></div>
        <div><img :src="cardVisa"/></div>
        <div><img :src="cardPaypal"/></div>
        <div><img :src="cardAmex"/></div>
        <div><img :src="cardJcb"/></div>
        <div><img :src="cardDiners"/></div>
      </div>
    </div>
  </q-card>
</template>

<script>
import { defineComponent } from "vue";
import lockImage from "assets/lock.svg";
import cardAmex from 'assets/payment/card-amex.png';
import cardVisa from 'assets/payment/card-visa.png';
import cardMaster from 'assets/payment/card-master.png';
import cardDiners from 'assets/payment/card-diners.png';
import cardPaypal from 'assets/payment/card-paypal.png';
import cardJcb from 'assets/payment/card-jcb.png';

export default defineComponent({
  name: "SafeCheckoutCard",
  data() {
    return {
      lockImage: lockImage,
      cardAmex: cardAmex,
      cardVisa: cardVisa,
      cardMaster: cardMaster,
      cardDiners: cardDiners,
      cardPaypal: cardPaypal,
      cardJcb: cardJcb
    }
  },
  setup() {
    return {};
  },
});
</script>

<style></style>
