<template>
  <div>
    <button class="buttonX" @click="closeSettings"> X </button>
    <h1>Personalização</h1>
    <br>
    <img center width="50%" src="src/assets/SpiderComicsLogo.jpeg">
    <br>
    <br>
    {{msg2}}
    <br>
    <button>Tema claro</button>
    <pre><button>Tema Escuro</button></pre>
    {{msg3}}
    <br>
    <button>Horizontal</button>
    <pre><button>Vertical</button></pre>
    {{msg}}
    <br>
    <button>Sim</button>
    <pre><button>Não</button></pre>
    <br>
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
      closeSettings () {
          this.$emit("read-mode", true)
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
