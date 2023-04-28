<template>
  <div class="paragraph-title">
    <span>{{paragraphTitle}}</span>
  </div>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "ParagraphTitle",
  props: {
    paragraphTitle: {
      type: String,
    },
  },
  setup() {
    return {};
  },
});
</script>

<style></style>
