<template>
  <div id="app">
    <SceneManager> </SceneManager>
  </div>
</template>

<script>
import SceneManager from "./components/SceneManager.vue";

export default {
  name: "App",
  components: {
    SceneManager
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
