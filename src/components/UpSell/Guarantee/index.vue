<template>
  <div class="upSell__GuaranteeSection">
    <q-card class="secure border-16 no-box-shadow">
      <div class="secure__content">
        <div>
          <img :src="lockImage"/>
          <p>Guaranteed <span>Safe</span> & <span>Secure</span> Checkout</p>
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
    <q-card class="support border-16 no-box-shadow">
      <div>
        <img :src="this.supportImage"/>
        <div>
          <p>27/7</p>
          <span>Support</span>
        </div>
      </div>
    </q-card>
  </div>
</template>

<script>
import { defineComponent } from "vue";
import supportImage from 'assets/support.svg';
import lockImage from 'assets/lock.svg';
import cardMaster from 'assets/payment/card-master.png';
import cardVisa from 'assets/payment/card-visa.png';
import cardPaypal from 'assets/payment/card-paypal.png';
import cardJcb from 'assets/payment/card-jcb.png';
import cardAmex from 'assets/payment/card-amex.png';
import cardDiners from 'assets/payment/card-diners.png';

export default defineComponent({
  name: "UpsellGuaranteeSection",
  data() {
    return {
      supportImage: supportImage,
      lockImage: lockImage,
      cardVisa: cardVisa,
      cardMaster: cardMaster,
      cardAmex: cardAmex,
      cardJcb: cardJcb,
      cardPaypal: cardPaypal,
      cardDiners: cardDiners
    }
  },
});
</script>
