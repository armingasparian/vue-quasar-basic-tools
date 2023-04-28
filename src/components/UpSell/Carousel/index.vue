<template>
  <div class="upSell__ImageSection">
    <div>
      <q-carousel
        animated
        v-model="slide"
        navigation
        infinite
        arrows
        :autoplay="autoplay"
        transition-prev="slide-right"
        transition-next="slide-left"
        @mouseenter="autoplay = false"
        @mouseleave="autoplay = true"
        class="full-height carouselSection"
      >
        <q-carousel-slide :name="1" :img-src="sneakers1"/>
        <q-carousel-slide :name="2" :img-src="sneakers2"/>
        <q-carousel-slide :name="3" :img-src="sneakers3"/>
        <q-carousel-slide :name="4" :img-src="sneakers4"/>
      </q-carousel>
    </div>
  </div>
</template>

<script>
import {defineComponent} from "vue";
import {ref} from 'vue';
import sneakers1 from "assets/products/sneakers-1.png";
import sneakers2 from "assets/products/sneakers-2.jpg";
import sneakers3 from "assets/products/sneakers-3.jpg";
import sneakers4 from "assets/products/sneakers-4.jpg";

export default defineComponent({
  name: "UpsellImageSection",
  setup() {
    return {
      slide: ref(1),
      autoplay: ref(true),
      sneakers1: sneakers1,
      sneakers2: sneakers2,
      sneakers3: sneakers3,
      sneakers4: sneakers4,
      fullscreen: ref(false)
    }
  }
});
</script>
