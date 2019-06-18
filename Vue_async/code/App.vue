<template>
  <div id="app">
    <HelloWorld :message="msg"/>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "app",
  components: {
    HelloWorld
  },
  data() {
    return {
      msg: ""
    };
  },
  async created() {
    this.msg = await "songzmin";
    console.log("wo shi shou ye");
  }
};
</script>

<style lang="less">
</style>
