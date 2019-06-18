<template>
  <div>{{data}}</div>
</template>

<script>
export default {
  props: ["message"],
  data() {
    return {
      data: ""
    };
  },
  created() {
    console.log(this.message);
  },
  watch: {
    message(val) {
      this.data = val;
    }
  }
};
</script>
<style scoped lang="less">
</style>
