<template>
  
    <button @click="showPopup = true">Show Popup</button>
    <PopupChild v-if="showPopup" @close="closePopup" />
  
</template>

<script>
import PopupChild from "./PopupChild.vue";

export default {
  name: "PopupParent",
  data() {
    return {
      showPopup: false,
    };
  },
  methods: {
      closePopup(valueFromEmit) { // reçoit en paramètre les données reçues de $emit
          this.showPopup = false;
          console.log(valueFromEmit);
      }
  },
  components: {
    PopupChild,
  },
};
</script>

<style scoped>
</style>