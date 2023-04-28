<template>
  <div class="relative-position input-style" :class="checkError">
    <img :src="phoneImage"/>
    <Field
      name="phone"
      type="number"
      v-model="phone"
      placeholder="Phone Number"
      :rules="isRequired"
    />
    <ErrorMessage name="phone"/>
  </div>
</template>

<script>
import {defineComponent} from "vue";
import phoneImage from "assets/phone.svg";
import {Field, ErrorMessage} from 'vee-validate';

export default defineComponent({
  name: "inputPhone",
  components: {
    Field,
    ErrorMessage
  },
  data() {
    return {
      phone: null,
      phoneImage: phoneImage,
      errorMessage: '',
      valid: true,
    }
  },
  methods: {
    isRequired(value) {
      if (!value) {
        this.valid = false;
        return 'This field is required';
      }
      if (!(value && value.trim())) {
        this.valid = false;
        return 'Enter a valid phone number';
      }
      return true
    },
  },
  computed: {
    checkError(){
      return ((this.valid===false && this.phone==='') ? 'error' : '');
    }
  }
});
</script>
