<template>
  <div class="orderCardMobile" :class="{'dropdown': dropdown}">
    <div class="orderCardMobile__summary" @click="openSummary">
      <div>
        <img :src="this.basketImage"/>
        <p>{{this.orderType}}</p>
        <img :src="this.arrowDown" />
      </div>
      <span>€69.00</span>
    </div>

    <div v-if="this.summary" class="orderCardMobile__dropdown">
      <order-card-content :displayType="displayType" />
    </div>
  </div>
</template>

<script>
import {defineComponent} from "vue";
import bootImage from "assets/boots.png";
import basketImage from "assets/basket.svg";
import arrowDown from "assets/arrow-down.svg";
import OrderCardContent from "components/OrderCardContent/OrderCardContent.vue";

export default defineComponent({
  name: "OrderCardMobile",
  components: {OrderCardContent},
  props: {
    displayType: {
      type: String,
      required: true,
    }
  },
  data() {
    return {
      bootImage: bootImage,
      basketImage: basketImage,
      arrowDown: arrowDown,
      summary: false,
      dropdown: false,
      orderType: 'Show order summary',
    }
  },
  methods: {
    openSummary() {
      this.summary = !this.summary;
      this.dropdown = !this.dropdown;
      if(this.summary) {
        this.orderType = 'Hide order summary';
      } else {
        this.orderType = 'Show order summary';
      }
      this.$emit('summary', this.summary)
    }
  },
});
</script>

<style></style>
