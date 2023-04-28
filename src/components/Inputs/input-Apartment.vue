<template>
  <div class="relative-position input-style" :class="checkError">
    <img :src="apartmentImage"/>
    <Field
      type="text"
      name="apartment"
      v-model="apartment"
      placeholder="Apartment, suit, etc (Optional)"
      :rules="isRequired"
    />
    <ErrorMessage name="apartment"/>
  </div>
</template>

<script>
import {defineComponent} from "vue";
import apartmentImage from "assets/apartment.svg";
import {Field, ErrorMessage} from 'vee-validate';

export default defineComponent({
  name: "inputApartment",
  components: {
    Field,
    ErrorMessage
  },
  data() {
    return {
      apartment: null,
      apartmentImage: apartmentImage,
      errorMessage: '',
      valid: true,
    }
  },
  methods: {
    isRequired(value) {
      if (!value) {
        this.valid = false;
        return 'Enter a Apartment';
      }
      return true
    },
  },
  computed: {
    checkError(){
      return ((this.valid===false && this.apartment==='') ? 'error' : '');
    }
  }
});
</script>


