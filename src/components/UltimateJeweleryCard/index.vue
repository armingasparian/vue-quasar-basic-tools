<template>
  <q-card flat class="jeweleryCard">
    <paragraph-title paragraphTitle="The ultimate jewellery club"/>
    <div class="jeweleryCard__content">
      <p>Ornare rhoncus nunc ut felis. Faucibus dolor at ultrices tincidunt.
        Pulvinar sed justo et viverra pellentesque.
      </p>
      <ul>
        <li><img :src="checkmarkImage"/>Extra 10$ off!</li>
        <li><img :src="checkmarkImage"/>Free shipping on marked club items!</li>
        <li><img :src="checkmarkImage"/>Free returns on marked club items!</li>
      </ul>
    </div>
  </q-card>
</template>

<script>
import {defineComponent} from "vue";
import ParagraphTitle from "components/Titles/ParagraphTitle.vue";
import checkmarkImage from "assets/checkmark.png";

export default defineComponent({
  name: "UltimateJeweleryCard",
  components: {ParagraphTitle},
  setup() {
    return {
      paragraphTitle: "paragraphTitle",
      checkmarkImage: checkmarkImage,
    };
  },
});
</script>

<style></style>
