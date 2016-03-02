<template>
  <h3 class="slide__title">Round 5: unknown width and height horizontal and vertical centering</h3>
  <pre id="slide11-css">.centered {
  position: relative;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}</pre>
  <div class="parent">
    <div class="center"></div>
  </div>
</template>

<script>
import hljs from 'highlight.js';

export default {
  ready() {
    hljs.highlightBlock(document.getElementById('slide11-css'));
  }
};
</script>

<style lang="scss" scoped>
.parent {
  width: 400px;
  height: 250px;
  background-color: #0097A7;
  margin: 0 auto;
  text-align: center;
}

.center {
  width: 100px;
  height: 100px;
  background-color: #35495E;
  position: relative;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  animation:
    1000ms ease-in infinite vertical-expand,
    1000ms ease-in infinite horizontal-expand;
}
</style>
