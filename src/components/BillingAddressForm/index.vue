<template>
  <div>
    <input-country/>
    <div class="name-lastname">
      <div>
        <input-name/>
      </div>
      <div>
        <input-last-name/>
      </div>
    </div>
    <input-address/>
    <input-apartment/>
    <div class="city-postcode">
      <div>
        <input-city/>
      </div>
      <div>
        <input-post-code/>
      </div>
    </div>
  </div>
</template>

<script>
import {defineComponent} from "vue";
import InputCountry from "components/Inputs/input-Country.vue";
import InputAddress from "components/Inputs/input-Address.vue";
import InputApartment from "components/Inputs/input-Apartment.vue";
import InputName from "components/Inputs/input-Name.vue";
import InputLastName from "components/Inputs/input-LastName.vue";
import InputCity from "components/Inputs/input-City.vue";
import InputPostCode from "components/Inputs/input-PostCode.vue";

export default defineComponent({
  name: "billingAddressForm",
  components: {
    InputPostCode,
    InputCity, InputLastName,
    InputName, InputApartment,
    InputAddress, InputCountry
  },
  data() {
    return {}
  },
  setup() {
    return {};
  },
});
</script>

<style></style>

