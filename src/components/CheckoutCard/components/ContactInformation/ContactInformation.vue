<template>
  <div class="contactInformation">
    <content-title :contentTitle="contentTitle"/>
    <div class="contactInformation__form">
      <input-email />
      <input-phone />
      <input-checkbox />
    </div>
  </div>
</template>

<script>
import {defineComponent} from "vue";
import ContentTitle from "components/Titles/ContentTitle.vue";
import InputEmail from "components/Inputs/input-Email.vue";
import InputPhone from "components/Inputs/input-Phone.vue";
import InputCheckbox from "components/Inputs/input-Checkbox.vue";

export default defineComponent({
  name: "ContactInformation",
  components: {
    InputCheckbox,
    InputPhone,
    InputEmail,
    ContentTitle,
  },
  data() {
    return {
      contentTitle: "Contact information",
    }
  },
  setup() {
    return {};
  },
});
</script>

<style></style>

