<template>
  <h1 class="slide__header">Let's Talk about CSS</h1>
</template>

<script>
export default {
  data () {
    return {
      // note: changing this line won't causes changes
      // with hot-reload because the reloaded component
      // preserves its current state and we are modifying
      // its initial state.
      msg: 'Slide 1'
    };
  }
};
</script>

<style lang="scss" scoped>
.slide--slide-1 {
}
</style>
