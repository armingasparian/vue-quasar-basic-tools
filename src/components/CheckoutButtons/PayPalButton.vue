<template>
  <div class="payPalButton">
    <button>
      <img :src="payPal"/>
    </button>
  </div>
</template>

<script>
import {defineComponent} from "vue";
import payPal from "assets/pay-pal.png";

export default defineComponent({
  name: "PayPallButton",
  data() {
    return {
      payPal: payPal,
    }
  },
  setup() {
    return {};
  },
});
</script>

<style></style>
