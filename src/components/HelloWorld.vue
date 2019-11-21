<template>
  <div>

    <div class="file is-boxed is-large is-warning is-centered">
      <label class="file-label">
        <input class="file-input" type="file" name="resume" multiple @change='getImage'>
        <span class="file-cta">
          UPLOAD
        </span>
      </label>
    </div>

  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      next_scene: false,
      frame: [],
      oie: [0,1,2,3]
    };
  },
  methods: {
    getImage(e) {
      let images = Array.from(e.target.files)

      for (let i = 0; i < images.length; i++) {
        let image = images[i];
        let reader = new FileReader();
        reader.readAsDataURL(image)
        reader.onload = e => {    
          this.frame.push(e.target.result)
          //alert(this.frame)
          this.$emit("frame", this.frame);
          this.$emit("next-scene", true);
        }
      }
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