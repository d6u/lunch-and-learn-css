<template>
  <h3 class="slide__title">Round 4: unknown height vertical centering</h3>
  <pre id="slide7-css">.center {
  width: 100px;
  margin-left: auto;
  margin-right: auto;
}</pre>
  <div class="center"></div>
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
.center {
  width: 100px;
  height: 100px;
  margin-left: auto;
  margin-right: auto;
  background-color: red;
}
</style>
