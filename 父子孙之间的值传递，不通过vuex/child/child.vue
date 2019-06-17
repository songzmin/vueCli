<template>
  <next v-bind="$attrs" v-on="$listeners"></next>
</template>
<script>
import Next from "./next/next.vue";
export default {
  components: {
    Next
  },
  inheritAttrs: false,
  props: ["val1"],
  created() {
    console.log(this.$attrs);
  }
};
</script>
<style scoped>
</style>
