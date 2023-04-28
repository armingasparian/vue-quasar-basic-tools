<template>
  <div class="googlePayButton">
    <button>
      <img :src="googlePay"/>
    </button>
  </div>
</template>

<script>
import {defineComponent} from "vue";
import googlePay from "assets/g-pay.png";

export default defineComponent({
  name: "GooglePayButton",
  data() {
    return {
      googlePay: googlePay,
    }
  },
  setup() {
    return {};
  },
});
</script>

<style></style>
