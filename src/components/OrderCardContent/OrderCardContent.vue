<template>
  <content-title :contentTitle="contentTitle"/>
  <div class="orderCard__summary">
    <div class="image-info">
      <div>
        <div>
          <img :src="bootImage"/>
          <p>1</p>
        </div>
        <p>Nike sneakers</p>
      </div>
      <p>€69.00</p>
    </div>
    <div class="disacount-code" :style="{display: displayType}">
      <input type="text" placeholder="Discount code"/>
      <button>Apply</button>
    </div>
    <div class="price-info">
      <div><p>Subtotal</p>
        <p class="value">€69.00</p></div>
      <div><p>Shipping</p>
        <p class="value">--</p></div>
      <div><p>Discount</p>
        <p class="value">--</p></div>
      <q-separator inset/>
      <div><p>Total</p>
        <p class="value">€69.00</p></div>
    </div>
  </div>
</template>

<script>
import {defineComponent} from "vue";
import ContentTitle from "components/Titles/ContentTitle.vue";
import bootImage from "assets/boots.png";

export default defineComponent({
  name: "OrderCardContent",
  components: {ContentTitle},
  props: {
    displayType: {
      type: String,
      required: true
    },
  },
  data() {
    return {
      contentTitle: "Order Summary",
      bootImage: bootImage,
    }
  },
  setup() {
    return {};
  },
});
</script>

<style></style>
