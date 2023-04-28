<template>
  <div class="relative-position input-style" :class="checkError">
    <img :src="dateImage" alt="card-date"/>
    <Field
      type="text"
      name="cardDate"
      v-model="cardDate"
      placeholder="MM/YY"
      maxlength='5'
      @keyup="formatString(event)"
    />
    <ErrorMessage name="cardDate"/>
  </div>
</template>

<script>
import {defineComponent} from "vue";
import dateImage from "assets/date.svg";
import {Field, ErrorMessage} from 'vee-validate';

export default defineComponent({
  name: "inputCardDate",
  components: {
    Field,
    ErrorMessage
  },
  data() {
    return {
      cardDate: null,
      dateImage: dateImage,
      errorMessage: '',
      valid: true,
    }
  },
  methods: {
    // :rules="isRequired"
    // isRequired(value) {
    //   if (!value) {
    //     this.valid = false;
    //     return 'Enter a valid date';
    //   }
    // },
    formatString(e) {
      this.cardDate = this.cardDate.replace(
        /^([1-9]\/|[2-9])$/g, '0$1/' // 3 > 03/
      ).replace(
        /^(0[1-9]|1[0-2])$/g, '$1/' // 11 > 11/
      ).replace(
        /^([0-1])([3-9])$/g, '0$1/$2' // 13 > 01/3
      ).replace(
        /^(0?[1-9]|1[0-2])([0-9]{2})$/g, '$1/$2' // 141 > 01/41
      ).replace(
        /^([0]+)\/|[0]+$/g, '0' // 0/ > 0 and 00 > 0
      ).replace(
        /[^\d\/]|^[\/]*$/g, '' // To allow only digits and `/`
      ).replace(
        /\/\//g, '/' // Prevent entering more than 1 `/`
      );
    }

  },
  computed: {
    checkError() {
      return ((this.valid === false && this.cardDate === '') ? 'error' : '');
    }
  }
});
</script>


