<template>
  <div class="relative-position input-style" :class="checkError">
    <img :src="userImage"/>
    <Field
      name="name"
      type="text"
      v-model="name"
      placeholder="First Name"
      :rules="isRequired"
    />
    <ErrorMessage name="name"/>
  </div>
</template>

<script>
import {defineComponent} from "vue";
import userImage from "assets/user.svg";
import {Field, ErrorMessage} from 'vee-validate';

export default defineComponent({
  name: "inputName",
  components: {
    Field,
    ErrorMessage
  },
  data() {
    return {
      name: null,
      userImage: userImage,
      errorMessage: '',
      valid: true,
    }
  },
  methods: {
    isRequired(value) {
      if (!value) {
        this.valid = false;
        return 'Enter a first name';
      }
      return true
    },
  },
  computed: {
    checkError(){
      return ((this.valid===false && this.name==='') ? 'error' : '');
    }
  }
});
</script>


