<template>
  <div class="relative-position input-style" :class="checkError">
    <img :src="cardImage" :class="this.cardImageStyle"/>
    <Field
      type="text"
      name="cardNumber"
      v-model="cardNumber"
      placeholder="2587 9860 2354"
      :rules="isRequired"
      @keyup="checkCardType"
    />
    <ErrorMessage name="cardNumber"/>
  </div>
</template>

<script>


import {defineComponent} from "vue";
import {Field, ErrorMessage} from 'vee-validate';
import cardImage from "assets/card.svg";
import cardVisa from "../../assets/payment/card-visa.png";
import cardMaster from "../../assets/payment/card-master.png";
import cardAmex from "../../assets/payment/card-amex.png";
import cardJcb from "../../assets/payment/card-jcb.png";
import cardDiners from "../../assets/payment/card-diners.png";


export default defineComponent({
  name: "inputCardNumber",
  components: {
    Field,
    ErrorMessage
  },
  data() {
    return {
      cardNumber: null,
      cardDefaultImage: cardImage,
      cardImage: cardImage,
      cardVisa: cardVisa,
      cardMaster: cardMaster,
      cardAmex: cardAmex,
      cardJcb: cardJcb,
      cardDiners: cardDiners,
      errorMessage: '',
      valid: true,
      cardType: null,
      cardImageStyle: '',
    }
  },
  methods: {
    isRequired(value) {
      if (!value) {
        this.valid = false;
        return 'Enter valid card number';
      }
      if (isNaN(value)) {
        this.valid = false;
        return 'Enter valid card number';
      }
      return true
    },
    checkCardType() {
      switch (this.cardNumber.slice(0, 2)) {
        case '40':
        case '41':
        case '42':
        case '43':
        case '44':
        case '45':
        case '46':
        case '47':
        case '48':
        case '49':
          this.cardType = 'Visa';
          this.cardImage = this.cardVisa;
          this.cardImageStyle = 'card-image-style';
          break;
        case '51':
        case '52':
        case '53':
        case '54':
        case '55':
          this.cardType = 'Master';
          this.cardImage = this.cardMaster;
          this.cardImageStyle = 'card-image-style';
          break;
        case '36':
        case '38':
          this.cardType = 'Diners';
          this.cardImage = this.cardDiners;
          this.cardImageStyle = 'card-image-style';
          break;
        case '34':
        case '37':
          this.cardType = 'Amex';
          this.cardImage = this.cardAmex;
          this.cardImageStyle = 'card-image-style';
          break;
        case '35':
          this.cardType = 'JCB';
          this.cardImage = this.cardJcb;
          this.cardImageStyle = 'card-image-style';
          break;
        default:
          this.cardType = 'other';
          this.cardImage = this.cardDefaultImage;
          this.cardImageStyle = '';
      }
    },
  },
  computed: {
    checkError() {
      return ((this.valid === false && this.cardNumber === '') ? 'error' : '');
    },
  }
});
</script>


