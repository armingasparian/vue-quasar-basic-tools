<template>
  <q-page class="upSell">
    <upsell-image-section/>
    <upsell-price-section/>
    <upsell-info-section/>
    <upsell-guarantee-section/>
    <div class="upSell__buttons">
      <a href="#/thank-you">
        <div class="agreement"><p>Yes, I want <img :src="this.arrowToRight"/></p></div>
      </a>
      <a href="#/">
        <div class="rejectment"><p>No, Thanks</p></div>
      </a>
    </div>
  </q-page>
</template>

<script>
import {defineComponent} from "vue";
import UpsellImageSection from "components/UpSell/Carousel/index.vue";
import UpsellPriceSection from "components/UpSell/Price/index.vue";
import UpsellInfoSection from "components/UpSell/Info/index.vue";
import UpsellGuaranteeSection from "components/UpSell/Guarantee/index.vue";
import arrowToRight from 'assets/arrow-to-right.svg';

export default defineComponent({
  name: "UpSell",
  components: {UpsellGuaranteeSection, UpsellInfoSection, UpsellPriceSection, UpsellImageSection},
  data() {
    return {
      arrowToRight: arrowToRight,
    }
  }
});
</script>
