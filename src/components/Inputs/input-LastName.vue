<template>
  <div class="relative-position input-style" :class="checkError">
    <img :src="userImage"/>
    <Field
      name="lastName"
      type="text"
      v-model="lastName"
      placeholder="Last Name"
      :rules="isRequired"
    />
    <ErrorMessage name="lastName"/>
  </div>
</template>

<script>
import {defineComponent} from "vue";
import userImage from "assets/user.svg";
import {Field, ErrorMessage} from 'vee-validate';

export default defineComponent({
  name: "inputLastName",
  components: {
    Field,
    ErrorMessage
  },
  data() {
    return {
      lastName: null,
      userImage: userImage,
      errorMessage: '',
      valid: true,
    }
  },
  methods: {
    isRequired(value) {
      if (!value) {
        this.valid = false;
        return 'Enter a last name';
      }
      return true
    },
  },
  computed: {
    checkError(){
      return ((this.valid===false && this.lastName==='') ? 'error' : '');
    }
  }
});
</script>


