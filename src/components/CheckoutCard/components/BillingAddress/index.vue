<template>
  <div class="billingAddress">
    <content-title :contentTitle="contentTitle"/>
    <p>Specify the address for your payment option</p>
    <div class="billingAddress__form">
      <div class="inputRadio-block">
        <input type="radio" id="3" value="Same as shipping address" v-model="color" @click="closeBillingForm"/>
        <label for="3">Same as shipping address</label>
      </div>
      <div :class="'inputRadio-block' + ' ' + (form ? 'opened' : '')">
        <div class="inputRadio-block__collection">
          <input type="radio" id="4" value="Use a different billing address" v-model="color" @click="openBillingForm"/>
          <label for="4">Use a different billing address</label>
        </div>
        <billing-address-form v-if="form"/>
      </div>
    </div>
  </div>
</template>

<script>
import {defineComponent, ref} from "vue";
import ContentTitle from "components/Titles/ContentTitle.vue";
import BillingAddressForm from "components/BillingAddressForm/index.vue";

export default defineComponent({
  name: "billingAddress",
  components: {
    BillingAddressForm,
    ContentTitle,
  },
  data() {
    return {
      contentTitle: "Billing address",
      color: ref('grey-9'),
      form: false,
    }
  },
  setup() {
    return {};
  },
  methods: {
    openBillingForm() {
      this.form = true
    },
    closeBillingForm() {
      this.form = false
    }
  }
});
</script>

<style></style>

