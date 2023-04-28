<template>
  <div class="shippingMethod">
    <content-title :contentTitle="contentTitle"/>
    <div class="shippingMethod__form">
      <div class="inputRadio-block">
        <input type="radio" id="1" value="Free Shipping" v-model="color" />
        <label for="1">Free Shipping</label>
      </div>
      <div class="inputRadio-block">
        <input type="radio" id="2" value="DHL with price" v-model="color" />
        <label for="2">DHL with price</label>
      </div>
    </div>
  </div>
</template>

<script>
import {defineComponent, ref} from "vue";
import ContentTitle from "components/Titles/ContentTitle.vue";

export default defineComponent({
  name: "ShippingMethod",
  components: {
    ContentTitle,
  },
  data() {
    return {
      contentTitle: "Shipping method",
      color: ref('grey-9'),
    }
  },
  setup() {
    return {};
  },
});
</script>

<style></style>

