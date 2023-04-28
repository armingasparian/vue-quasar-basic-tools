<template>
    <div class="page-title">
      <span>{{pageTitle}}</span>
    </div>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "PageTitle",
  props: {
    pageTitle: {
      type: String,
    },
  },
  setup() {
    return {};
  },
});
</script>

<style></style>
