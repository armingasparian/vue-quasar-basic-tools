<template>
  <div class="lifetimeWarranty border-16">
    <paragraph-title :paragraphTitle="paragraphTitle"/>
    <div class="lifetimeWarranty__add">
      <p>Add a lifetime warranty & enjoy peace of mind
        for life with your dream collections order for just $4.99</p>
      <div>
        <p>Add-<br/>$4.99</p>
      </div>
    </div>
  </div>
</template>

<script>
import {defineComponent} from "vue";
import ParagraphTitle from "components/Titles/ParagraphTitle.vue";

export default defineComponent({
  name: "LifetimeWarranty",
  components: {
    ParagraphTitle,
  },
  data() {
    return {
      paragraphTitle: "Lifetime Warranty🔥",
    }
  },
  setup() {
    return {};
  },
});
</script>

<style></style>

