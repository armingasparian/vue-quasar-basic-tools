<template>
  <div class="content-title">
    <span>{{contentTitle}}</span>
  </div>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "ContentTitle",
  props: {
    contentTitle: {
      type: String,
    },
  },
  setup() {
    return {};
  },
});
</script>

<style></style>
