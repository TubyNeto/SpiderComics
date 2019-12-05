<template>
     <div>
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
                      <img width="25px" src="https://image.flaticon.com/icons/svg/660/660770.svg" />
                    </li>
                    <div class="select">
                      <select>
                        <option>Tema Claro</option>
                        <option>Tema Escuro</option>
                      </select>
                    </div>
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
</template>

<script>
export default {
    
}
</script>

<style scoped>

</style>
