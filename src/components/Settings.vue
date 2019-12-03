<template>
  <div id="app">
    <SceneManager></SceneManager>
    <div class="modal is-active" id="option">
      <div class="modal-background"></div>
      <div class="modal-card">
        <header class="modal-card-head">
          <p class="modal-card-title">Opções</p>
          <button class="delete" aria-label="close"></button>
        </header>
        <section class="modal-card-body">
          <h2>Modo de leitura</h2>
          <br />
          <br />

          <div class="controle">
            <label class="radio">
              <input type="radio" name="foobar" />
              Vertical
            </label>
            <br />
            <label class="radio">
              <input type="radio" name="foobar" checked />
              Horizontal
            </label>
          </div>

          <hr />
          <label class="checkbox">
            Modo escuro
            <input type="checkbox" />
          </label>

          <hr />
          <label class="checkbox">
            Redimensionar imagens
            <input type="checkbox" />
          </label>
        </section>
        <footer class="modal-card-foot">
          <button class="button is-success">Salvar</button>
        </footer>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      msg: "Gostaria de redimensionar automaticamente a imagem?",
      msg2: "Qual tema de tela você quer?",
      msg3: "Como você quer ler?"
    };
  },
  methods: {
    closeSettings() {
      this.$emit("read-mode", true);
    }
  }
};
</script>

<style scoped>
h1 {
  font-family: cursive, optima;
}

button {
  background-color: rgb(228, 83, 83);
  color: rgb(0, 0, 0);
  border: 3px mixed #ddd;
  border-radius: 4px;
  font-family: "Courier New", Courier, monospace;
}
#app {
  font-stretch: expanded;
  font-family: "Courier New", Courier, monospace;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #649b40;
  background-color: #070c2b;
}
buttonX {
  margin-left: 30px;
}
</style>
