<template>
  <div>

    <div class="file is-boxed is-large is-warning is-centered">
      <label class="file-label">
        <input class="file-input" type="file" name="resume" @change='getImage'>
        <span class="file-cta">
          UPLOAD
        </span>
      </label>
    </div>
   
    <img :src="frame">

  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      next_scene: false,
      frame: null
    };
  },
  methods: {
    getImage(e) {
      let image = e.target.files[0];
      let reader = new FileReader();
      reader.readAsDataURL(image);
      reader.onload = e => {    
        this.$emit("frame", e.target.result);
        this.$emit("next-scene", true);
      };
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
