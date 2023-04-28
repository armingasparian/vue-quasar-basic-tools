<template>
  <q-card flat no-shadow class="thankYouCard">
    <order-card-mobile v-if="widthLessThan769" displayType="none" />
    <div class="thankYouCard__content">
      <div class="logo">
        <img :src="this.thankYouLogo"/>
      </div>
      <div class="title">
        <p>Thank you for your order</p>
        <span>Your order is confirmed</span>
      </div>
      <div class="button">
        <a href="#/upsell">
          <div>
            <p><img :src="this.arrowToRight"/> Back to Shop</p>
          </div>
        </a>
      </div>
      <div class="order-info border-16">
        <div>
          <p class="heading">Name:</p>
          <p class="info">Oleo Bone</p>
        </div>
        <div>
          <p class="heading">Email:</p>
          <p class="info">oleo_bone@gmail.com</p>
        </div>
        <div>
          <p class="heading">Ship to:</p>
          <p class="info">4140 Parker Rd. Allentown, New Mexico 31134</p>
        </div>
        <div>
          <p class="heading">Bill to:</p>
          <p class="info">4140 Parker Rd. Allentown, New Mexico 31134</p>
        </div>
        <div>
          <p class="heading">Payment:</p>
          <p class="info">Credit Card</p>
        </div>
      </div>
    </div>
  </q-card>
</template>

<script>
import {defineComponent} from "vue";
import thankYouLogo from 'assets/thank-you-logo.svg';
import arrowToRight from 'assets/arrow-to-right.svg';
import OrderCardMobile from "components/OrderCardMobile/index.vue";
import { useWindowSize } from 'vue-window-size';

export default defineComponent({
  name: "ThankYouCard",
  components: {OrderCardMobile},
  setup() {
    const { width } = useWindowSize();
    return {
      windowWidth: width,
    };
  },
  data() {
    return {
      thankYouLogo: thankYouLogo,
      arrowToRight: arrowToRight,
    }
  },
  computed: {
    widthLessThan769() {
      return this.windowWidth < 769
    },
  },
});
</script>
