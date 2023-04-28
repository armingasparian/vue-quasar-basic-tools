<template>
  <div>
    <input-card-number/>
    <input-card-user/>
    <div class="mm-cvv">
      <div>
        <input-card-date/>
      </div>
      <div>
        <input-c-v-v/>
      </div>
    </div>
  </div>
</template>

<script>
import {defineComponent} from "vue";
import InputCardNumber from "components/Inputs/input-CardNumber.vue";
import InputCardUser from "components/Inputs/input-CardUser.vue";
import InputCardDate from "components/Inputs/input-CardDate.vue";
import InputCVV from "components/Inputs/input-CVV.vue";

export default defineComponent({
  name: "creditCardForm",
  components: {
    InputCVV,
    InputCardDate,
    InputCardUser,
    InputCardNumber,
  },
});
</script>

<style></style>

