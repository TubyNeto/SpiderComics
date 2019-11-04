<template>
  <div>
    <HelloWorld v-if="!passScene" 
      @next-scene="passScene = $event"
      @frame="framer = $event"
      ></HelloWorld>
    <Reader v-else :frame="framer"></Reader>
  </div>
</template>

<script>
import Reader from "./Reader.vue";
import HelloWorld from "./HelloWorld.vue";

export default {
  data() {
    return {
      passScene: false,
      framer: null
    };
  },
  components: {
    Reader,
    HelloWorld
  },
  methods: {
    pasScene() {
      this.passScene = true;
    }
  }
};
</script>

<style scoped>
</style>
