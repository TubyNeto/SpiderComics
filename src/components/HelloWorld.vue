<template>
  <div class="hello">
    <button @click="initialMethod" class="button is-rounded is-large is-warning">Upload</button>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data () {
    return {
      next_scene: false
    }
  }, 
  methods: {
    initialMethod() {
      alert("Aqui sera feito o Upload");
      this.$emit('next-scene', true)
    }
  },
  props: {
    nextScene: {
      type: Boolean || Number || Array || Object,
      default: false,
      required: false
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
.botao {
  color: #ffffff;
}
</style>
