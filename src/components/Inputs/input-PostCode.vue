<template>
  <div class="relative-position input-style" :class="checkError">
    <Field
      type="text"
      name="postCode"
      v-model="postCode"
      placeholder="Post code"
      :rules="isRequired"
    />
    <ErrorMessage name="postCode"/>
  </div>
</template>

<script>
import {defineComponent} from "vue";
import {Field, ErrorMessage} from 'vee-validate';

export default defineComponent({
  name: "inputPostCode",
  components: {
    Field,
    ErrorMessage
  },
  data() {
    return {
      postCode: null,
      errorMessage: '',
      valid: true,
    }
  },
  methods: {
    isRequired(value) {
      if (!value) {
        this.valid = false;
        return 'Enter a City';
      }
      if (isNaN(value)) {
        this.valid = false;
        return 'Enter a number';
      }
      return true
    },
  },
  computed: {
    checkError(){
      return ((this.valid===false && this.postCode==='') ? 'error' : '');
    }
  }
});
</script>


