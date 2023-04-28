<template>
  <q-checkbox v-model="checkbox" label="Sign up for exclusive offers and news" class="checkbox-style"
              :key="Math.random()"/>
</template>

<script>
import {defineComponent, ref} from "vue";

export default defineComponent({
  name: "inputCheckbox",
  data() {
    return {
      checkbox: ref(false),
    }
  },
});
</script>


