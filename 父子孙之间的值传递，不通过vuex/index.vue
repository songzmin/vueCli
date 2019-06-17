<template>
  <child :second="second" :third="third" @func1="Func1Click" @func2="Func2Click"></child>
</template>
<script>
import child from "./child/child.vue";
export default {
  components: {
    child
  },
  data() {
    return {
      second: "props second",
      third: "props third"
    };
  },
  methods: {
    Func1Click(val) {
      this.second = val;
    },
    Func2Click(val) {
      this.third = val;
    }
  }
};
</script>
<style scoped>
</style>
