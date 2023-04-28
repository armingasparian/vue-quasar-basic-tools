<template>
  <div class="relative-position input-style" :class="checkError">
    <Field
      type="text"
      name="city"
      v-model="city"
      placeholder="City"
      :rules="isRequired"
    />
    <ErrorMessage name="city"/>
  </div>
</template>

<script>
import {defineComponent} from "vue";
import {Field, ErrorMessage} from 'vee-validate';

export default defineComponent({
  name: "inputCity",
  components: {
    Field,
    ErrorMessage
  },
  data() {
    return {
      city: null,
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
      return true
    },
  },
  computed: {
    checkError(){
      return ((this.valid===false && this.city==='') ? 'error' : '');
    }
  }
});
</script>


