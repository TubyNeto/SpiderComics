<template>
<div v-if="!openedSettings">
    <div class="field has-addons has-addons-centered">
      <section class="hero">
        <div class="hero is-light">
          <nav class="level">
           <a class="navbar">
              <img width="60px" src="https://diyuehb.com/images/angry-saber-4.png"/>
            </a>
            <div class="hero-foot">
              <nav class="tabs is-boxed is-fullwidht">
                <div class="container">
                  <ul>
                    <li class="level-item has-text-centered">
                      <a class="link is-info">Inicio</a>
                    </li>
                    <li class="level-item has-text-centered">
                      <a class="link is-info">Mangas Salvos</a>
                    </li>

                    <div class="file is-normal is-link">
                      <label class="file-label">
                        <input
                          class="file-input"
                          type="file"
                          name="resume"
                          multiple
                          @change="getImage"
                        />
                        <span class="file-cta">UPLOAD</span>
                      </label>
                    </div>
                    <li></li>
                    <li class="level-item has-text-centered">
                      <a @click="openSettings">
                        <img width="25px" src="https://image.flaticon.com/icons/svg/660/660770.svg" />
                      </a>
                    </li>
                    
                  </ul>
                </div>
              </nav>
            </div>

            <div class="level">
              <div class="field has-addons">
                <p class="control">
                  <input class="input" type="text" placeholder="Pesquisar manga" />
                </p>
                <button class="button is-link is-outlined">Pesquisar</button>
              </div>
            </div>
          </nav>
        </div>
      </section>
    </div>
  </div>
  <div v-else>
      <Settings @pass="closeSettings()"></Settings>
  </div>
</template>

<script>
import Settings from "./Settings.vue";
export default {
  name: "HelloWorld",
  components: {
      Settings
  },
  data() {
    return {
      next_scene: false,
      frame: [],
      oie: [0, 1, 2, 3],
      temaClaro: true,
      temaEscuro: false,
      openedSettings: false
    };
  },
  methods: {
    getImage(e) {
      let images = Array.from(e.target.files);

      for (let i = 0; i < images.length; i++) {
        let image = images[i];
        let reader = new FileReader();
        reader.readAsDataURL(image);
        reader.onload = e => {
          this.frame.push(e.target.result);
          //alert(this.frame)
          this.$emit("frame", this.frame);
          this.$emit("next-scene", true);
        };
      }
    },
    openSettings() {
        this.openedSettings = true
    },
    closeSettings() {
        this.openedSettings = false
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
body {
    z-index: 2;
}
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
