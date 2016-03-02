<template>
  <h3 class="slide__title">Round 2: unknown width horizontal centering</h3>
  <pre id="slide8-css">.parent {
  text-align: center;
}
.centered {
  display: inline-block;
}</pre>
  <div class="parent">
    <div class="center"></div>
  </div>
</template>

<script>
import hljs from 'highlight.js';

export default {
  ready() {
    hljs.highlightBlock(document.getElementById('slide8-css'));
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
  height: 100px;
  background-color: #35495E;
  display: inline-block;
  animation: 1000ms ease-in infinite horizontal-expand;
}

@keyframes horizontal-expand {
  from {
    width: 100px;
  }
  50% {
    width: 200px;
  }
  to {
    width: 100px;
  }
}
</style>
