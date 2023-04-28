<template>
  <div class="relative-position input-style" :class="checkError">
    <img :src="lockImage"/>
    <Field
      type="text"
      name="cvv"
      v-model="cvv"
      placeholder="CVV"
      :rules="isRequired"
    />
    <ErrorMessage name="cvv"/>
  </div>
</template>

<script>
import {defineComponent} from "vue";
import lockImage from "assets/lock.svg";
import {Field, ErrorMessage} from 'vee-validate';

export default defineComponent({
  name: "inputCVV",
  components: {
    Field,
    ErrorMessage
  },
  data() {
    return {
      cvv: null,
      lockImage: lockImage,
      errorMessage: '',
      valid: true,
    }
  },
  methods: {
    isRequired(value) {
      if (!value) {
        this.valid = false;
        return 'Enter a CVV';
      }
      if (isNaN(value)) {
        this.valid = false;
        return 'Enter a number';
      }
      if (!isNaN(value) && value.length <= 3) {
        return true
      }
      this.valid = false;
      return "Enter a valid CVV"
    },
  },
  computed: {
    checkError(){
      return ((this.valid===false && this.cvv==='') ? 'error' : '');
    }
  }
});
</script>


