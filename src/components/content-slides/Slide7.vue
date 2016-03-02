<template>
  <h3 class="slide__title">Round 1: horizontal centering</h3>
  <pre id="slide7-css">.center {
  width: 100px;
  margin-left: auto;
  margin-right: auto;
}</pre>
  <div class="parent">
    <div class="center"></div>
  </div>
</template>

<script>
import hljs from 'highlight.js';

export default {
  ready() {
    hljs.highlightBlock(document.getElementById('slide7-css'));
  }
};
</script>

<style lang="scss" scoped>
.parent {
  width: 400px;
  height: 250px;
  background-color: #0097A7;
  margin: 0 auto;
}
.center {
  width: 100px;
  height: 100px;
  margin-left: auto;
  margin-right: auto;
  background-color: #35495E;
}
</style>
