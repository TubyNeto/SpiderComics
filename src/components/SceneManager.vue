<template>
  <div>
    <HelloWorld @next-scene="passScene = $event" @frame="framer = $event"></HelloWorld>
    <br>
    <div v-if="passScene">
      <div v-if="readMode">
        <Reader :frame="framer"></Reader>
      </div>

      <div v-else>
        <Settings @read-mode="readMode = $event"></Settings>
      </div>
    </div>
  </div>
</template>

<script>
import Reader from "./Reader.vue";
import HelloWorld from "./HelloWorld.vue";
import Settings from "./Settings.vue";
export default {
  data() {
    return {
      passScene: false,
      framer: null,
      readMode: true
    };
  },
  components: {
    Reader,
    HelloWorld,
    Settings
  },
  methods: {
    pasScene() {
      this.passScene = true;
    },
  }
};
</script>

<style scoped>
</style>