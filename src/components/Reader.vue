<template>
  <div>
    <article class="tile is-child notification is-dark">

    <div v-for='(item, index) in frame' :key="index">
      <img :src="item">
    </div>
    </article>
  </div>
</template>

<script>
export default {
  props: {
    frame: {
      type: Object || Boolean || Array || Number || Function,
      required: false
    }
  },
  data () {
    return {
    }
  }
};
</script>

<style scoped>
</style>