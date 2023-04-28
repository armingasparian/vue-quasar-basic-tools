<template>
  <q-card flat class="orderCard">
    <order-card-content :displayType="displayType"/>
  </q-card>
</template>

<script>
import {defineComponent} from "vue";
import bootImage from "assets/boots.png";
import OrderCardContent from "components/OrderCardContent/OrderCardContent.vue";

export default defineComponent({
  name: "OrderCard",
  components: {OrderCardContent},
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
