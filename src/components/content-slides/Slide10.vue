<template>
  <h3 class="slide__title">Round 4: unknown height vertical centering</h3>
  <pre id="slide10-css">.centered {
  position: relative;
  top: 50%;
  transform: translateY(-50%);
}</pre>
  <div class="parent">
    <div class="center"></div>
  </div>
</template>

<script>
import hljs from 'highlight.js';

export default {
  ready() {
    hljs.highlightBlock(document.getElementById('slide10-css'));
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
  transform: translateY(-50%);
  animation: 1000ms ease-in infinite vertical-expand;
}

@keyframes vertical-expand {
  from {
    height: 100px;
  }
  50% {
    height: 200px;
  }
  to {
    height: 100px;
  }
}
</style>
