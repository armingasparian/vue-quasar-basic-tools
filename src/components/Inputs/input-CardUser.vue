<template>
  <div class="relative-position input-style" :class="checkError">
    <img :src="userImage"/>
    <Field
      class="user-card-input"
      type="text"
      name="cardUserName"
      v-model="cardUserName"
      placeholder="Name on the card"
      :rules="isRequired"
      style="text-transform: uppercase"
    />
    <ErrorMessage name="cardUserName"/>
  </div>
</template>

<script>
import {defineComponent} from "vue";
import userImage from "assets/user.svg";
import {Field, ErrorMessage} from 'vee-validate';

export default defineComponent({
  name: "inputCardUser",
  components: {
    Field,
    ErrorMessage
  },
  data() {
    return {
      cardUserName: null,
      userImage: userImage,
      errorMessage: '',
      valid: true,
    }
  },
  methods: {
    isRequired(value) {
      if (!value) {
        this.valid = false;
        return 'Enter a valid user name';
      }
      const regex = /^[A-Za-z' ']*$/;
      if (!regex.test(value)) {
        this.valid = false;
        return 'Enter a valid user name';
      }
      return true
    }
  },
  computed: {
    checkError(){
      return ((this.valid===false && this.cardUserName==='') ? 'error' : '');
    }
  }
})
;
</script>


