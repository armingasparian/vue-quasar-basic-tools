<template>
  <div class="relative-position input-style" :class="checkError">
    <img :src="emailImage"/>
    <Field
      name="email"
      type="email"
      v-model="email"
      placeholder="Email Address"
      :rules="validateEmail"
    />
    <ErrorMessage name="email"/>
  </div>
</template>

<script>
import {defineComponent} from "vue";
import emailImage from "assets/email.svg";
import {Field, ErrorMessage} from 'vee-validate';

export default defineComponent({
  name: "inputEmail",
  components: {
    Field,
    ErrorMessage
  },
  data() {
    return {
      email: null,
      errorMessage: '',
      emailImage: emailImage,
      valid: true,
    }
  },
  methods: {
    validateEmail(value) {
      if (!value) {
        this.valid = false;
        return 'This field is required';
      }
      const regex = /^[A-Z0-9._%+-]+@[A-Z0-9.-]+\.[A-Z]{2,4}$/i;
      if (!regex.test(value)) {
        this.valid = false;
        return 'Enter a valid email address';
      }
      return true;
    },
  },
  computed: {
    checkError() {
      return ((this.valid === false && this.email === '') ? 'error' : '');
    }
  }
});
</script>


