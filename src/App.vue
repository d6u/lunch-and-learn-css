<template>
  <div class="app">
    <slide :current-slide="currentSlide"><slide1></slide1></slide>
  </div>
</template>

<script>
import Slide from './components/Slide';
import Slide1 from './components/Slide1';
// import Slide2 from './components/Slide2';

const data = {
  currentSlide: 0
};

export default {
  data,
  components: {
    Slide,
    Slide1
  }
};
</script>

<style lang="scss">
@import './css/normalize.css';
@import './css/skeleton.css';

*, *::before, *::after {
  box-sizing: border-box;
}

html {
  font-size: 10px;
}

body {
  font-family: 'Playfair Display', serif;
}

.app {
  height: 100vh;
  width: 100vw;
  position: relative;
}
</style>
