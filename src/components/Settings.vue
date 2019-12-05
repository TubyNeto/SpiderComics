<template>
  <div id="app">
    <div class="modal is-active" id="option">
      <div @click="closeSettings" class="modal-background"></div>
      <div class="modal-card">
        <header class="modal-card-head">
          <p class="modal-card-title">Opções</p>
          <button @click="closeSettings" class="delete" aria-label="close"></button>
        </header>
        <section class="modal-card-body">
          <h2>Modo de leitura</h2>
          <br>
            <div class="controle">
              <label class="radio">
                <input type="radio" id="vertical" name="foobar" v-model="orientado">
                Vertical
              </label>
              <br>
              <label class="radio">
                <input type="radio" id="horizontal" name="foobar" checked v-model="orientado">
                Horizontal
              </label>
            </div>

          <hr>
          <label class="checkbox">
            Modo escuro 
            <input type="checkbox" id="darkmode" @change="saveOptions">
          </label>
          <label for="checkbox">{{isdark}}</label>
          <hr>
          <label class="checkbox">
            Redimensionar imagens 
            <input type="checkbox" id="resizeimages" v-model="isresized">>
            <label for="checkbox">{{isresized}}</label>
          </label>
        </section>
        <footer class="modal-card-foot">
          <button class="button is-success" @click="persist">
            Salvar
          </button>
        </footer>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data: {
    orientado: "vertical",
    isDark: false,
    isResized: false
  },
  mounted(){
    if (localStorage.orientado){
      this.orientado = localStorage.orientado
    }
    if (localStorage.isDark){
      this.isDark = localStorage.isDark
    }if (localStorage.isResized){
      this.isResized = localStorage.isResized
    }
  },
  methods: {
    saveOptions() {
      this.isDark = true
    },
    persist() {
      localStorage.orientado = this.orientado;
      localStorage.isDark = this.isDark;
      localStorage.isResized = this.isResized;
      console.log(localStorage.orientado);
      console.log(localStorage.isDark);
      console.log(localStorage.isResized);
    },
    closeSettings() {
      this.$emit("pass", false);
    }
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