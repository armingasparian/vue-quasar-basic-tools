<template>
  <div class="relative-position input-style">
    <img :src="countryImage"/>
    <select>
      <option v-for="option in options" :key="option.id">
        {{ option.text }}
      </option>
    </select>
  </div>
</template>


<script>
import {defineComponent} from "vue";
import countryImage from "assets/country.svg";

export default defineComponent({
  name: "inputCountry",
  data() {
    return {
      country: '',
      countryImage: countryImage,
      options: [
        {id: 0, text: 'Select a Country', value: '', disables: true, selected: true},
        {id: 1, text: 'USA', value: 'USA', disables: false, selected: false},
        {id: 2, text: 'UK', value: 'UK', disables: false, selected: false},
        {id: 3, text: 'India', value: 'India', disables: false, selected: false}
      ],
    }
  },
});
</script>
