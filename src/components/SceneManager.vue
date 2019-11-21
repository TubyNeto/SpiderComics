<template>
  <div>

    <HelloWorld v-if="!passScene" 
      @next-scene="passScene = $event"
      @frame="framer = $event"
      ></HelloWorld>

    <div v-else>

      <div v-if='readMode'>
        <button class="is-normal is-primary is-centered" @click='aqui'>CONFIGURAÇÕES</button>
        <Reader :frame="framer"></Reader>
      </div>

      <div v-else>
        <Settings @read-mode="readMode = $event"> </Settings> 
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
    aqui (){
      this.readMode = false
    }
  }
};
</script>

<style scoped>
</style>