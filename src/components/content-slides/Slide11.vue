<template>
  <h3 class="slide__title">Round 5: unknown width and height horizontal and vertical centering</h3>
  <div class="side-by-side-wrapper">
    <div class="left">
      <pre id="slide11-css">.centered {
  position: relative;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}</pre>
    </div>
    <div class="right">
      <div class="parent">
        <div class="center"></div>
      </div>
    </div>
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
.smaller-code-block {
  font-size: 2rem;
}

.side-by-side-wrapper {
  position: relative;
}

.left {
  width: 650px;
  height: 400px;
}

.right {
  width: 1200px - 650px;
  position: absolute;
  right: 0;
  top: 0;
  height: 100%;
}

.parent {
  width: 400px;
  height: 250px;
  background-color: #0097A7;
  position: relative;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
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
