<template>
  <div class="relative-position input-style" :class="checkError">
    <img :src="addressImage"/>
    <Field
      type="text"
      name="address"
      v-model="address"
      placeholder="Address"
      :rules="isRequired"
    />
    <ErrorMessage name="address"/>
  </div>
</template>

<script>
import {defineComponent} from "vue";
import addressImage from "assets/address.svg";
import {Field, ErrorMessage} from 'vee-validate';

export default defineComponent({
  name: "inputAddress",
  components: {
    Field,
    ErrorMessage
  },
  data() {
    return {
      address: null,
      addressImage: addressImage,
      errorMessage: '',
      valid: true,
    }
  },
  methods: {
    isRequired(value) {
      if (!value) {
        this.valid=false;
        return 'Enter a Address';
      }
      return true
    },
  },
  computed: {
    checkError(){
      return ((this.valid===false && this.address==='') ? 'error' : '');
    }
  }
});
</script>


