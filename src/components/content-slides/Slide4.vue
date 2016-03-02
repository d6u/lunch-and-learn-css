<template>
  <h3 class="slide__title">What it looks like</h3>
  <div class="center" id="slide4-css">
    <pre>.container::before,
.container::after,
.container:before,
.container:after {
  content: '';
  display: block;
  width: 100px;
  height: 100px;
  background-color: red;
}</pre>
  </div>
</template>

<script>
import hljs from 'highlight.js';

export default {
  ready() {
    hljs.highlightBlock(document.getElementById('slide4-css'));
  }
};
</script>

<style lang="scss" scoped>
.center {
  width: 500px;
  margin: 40px auto 0;
}
</style>
