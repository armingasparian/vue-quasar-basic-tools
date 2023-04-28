<template>
  <q-card flat class="paymentMethodCard">
    <content-title :contentTitle="contentTitle"/>
    <div class="paymentMethodCard__content">
      <div class="paymentMethodCard__form">
        <div :class="'inputRadio-block cards' + ' ' + (cardForm ? 'opened' : '')">
          <div>
            <input type="radio" id="5" value="Credit Card" v-model="color" @click="openCreditCard"/>
            <label for="5">Credit Card</label>
            <div class="card-types">
              <img :src="cardMaster"/>
              <img :src="cardAmex"/>
              <img :src="cardVisa"/>
              <button>
                & more
              </button>
            </div>
          </div>
          <credit-card-form v-if="cardForm"/>
        </div>
        <div class="inputRadio-block paypal">
          <div class="inputRadio-block__collection">
            <input type="radio" id="6" value="Paypal" v-model="color" @click="openPayPal"/>
            <label for="6">Paypal</label>
            <div class="card-types">
              <img :src="cardPaypalFull"/>
            </div>
          </div>
        </div>
        <div class="billing-contract">
          <input type="checkbox"/>
          <p>By checking this box, I acknowledge that I have read and agree to
            the <span>Terms of Service</span>, and <span>Monthly Billing Terms</span> of this website
            and want to opt-in for the monthly billed Dream Collection Club®</p>
        </div>
        <div class="complete-purchase">
          <button>
            Complete Purchase
          </button>
        </div>
      </div>
    </div>
  </q-card>
</template>

<script>
import {defineComponent, ref} from "vue";
import ContentTitle from "components/Titles/ContentTitle.vue";
import cardMaster from 'assets/payment/card-master.png';
import cardAmex from 'assets/payment/card-amex.png';
import cardVisa from 'assets/payment/card-visa.png';
import cardPaypalFull from 'assets/payment/card-paypal-full.png';
import CreditCardForm from "components/PaymentMethodCard/CreditCardForm/index.vue";

export default defineComponent({
  name: "PaymentMethodCard",
  components: {CreditCardForm, ContentTitle},
  data() {
    return {
      contentTitle: "Payment Method",
      color: ref('grey-9'),
      cardAmex: cardAmex,
      cardVisa: cardVisa,
      cardMaster: cardMaster,
      cardPaypalFull: cardPaypalFull,
      cardForm: false,
    }
  },
  methods: {
    openCreditCard() {
      this.cardForm = true
    },
    openPayPal() {
      this.cardForm = false
    }
  }
});
</script>

<style></style>
