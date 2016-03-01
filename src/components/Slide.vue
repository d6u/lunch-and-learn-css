<template>
  <div class="slide" v-bind:style="{transform: transform}">
    {{currentSlide}}
    <slot>
  </div>
</template>

<script>
export default {
  data () {
    return {
      // note: changing this line won't causes changes
      // with hot-reload because the reloaded component
      // preserves its current state and we are modifying
      // its initial state.
      transform: `translateX(100vw)`
    };
  }
};
</script>

<style lang="scss">
.slide {
  --border-color: #5B2C6F;
  --background-color: #FEF5E7;
  height: 100vh;
  width: 100vw;
  border: 20px solid var(--border-color);
  background-color: var(--background-color);
  position: absolute;
  top: 0;
  left: 0;
}

.slide__header {
  position: relative;
  top: 50%;
  transform: translateY(-50%);
  text-align: center;
  font-size: 10rem;
}

</style>
