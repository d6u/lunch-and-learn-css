<template>
  <h3 class="slide__title">Round 6: unknown width and height horizontal and vertical super-duper IE8 compatible don't know why you care centering</h3>
  <div class="side-by-side-wrapper">
    <div class="left">
      <pre class="smaller-code-block" id="slide12-css">.parent {
  text-align: center;
  white-space: nowrap;
}
.parent::before { /* Very cool ::before usage */
  content: '';
  display: inline-block;
  height: 100%;
  vertical-align: middle;
  margin-right: -0.25em; /* Adjusts for spacing */
}
.centered {
  display: inline-block;
  vertical-align: middle;
  /* Any width or height */
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
    hljs.highlightBlock(document.getElementById('slide12-css'));
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
  height: 300px;
  background-color: #0097A7;
  position: relative;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);

  text-align: center;
  white-space: nowrap;
  &::before {
    content: '';
    display: inline-block;
    height: 100%;
    vertical-align: middle;
    margin-right: -0.25em; /* Adjusts for spacing */
  }
}

.center {
  width: 100px;
  height: 100px;
  background-color: #35495E;
  animation:
    1000ms ease-in infinite vertical-expand,
    1000ms ease-in infinite horizontal-expand;
  display: inline-block;
  vertical-align: middle;
}
</style>
