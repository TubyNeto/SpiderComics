<template>
  <div>
    <article class="tile is-child notification is-dark">
      <img :src="frame">
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
