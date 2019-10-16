<template>
  <div>
    <HelloWorld v-if="!passScene" @next-scene="passScene = $event"></HelloWorld>
    <Reader v-else></Reader>
  </div>
</template>

<script>
import Reader from "./Reader.vue";
import HelloWorld from "./HelloWorld.vue";

export default {
  data() {
    return {
      passScene: false
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
