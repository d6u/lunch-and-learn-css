<template>
  <div class="app">
    <slide :prev="prev" :current="current" :index="0"><slide1></slide1></slide>
    <slide :prev="prev" :current="current" :index="1"><slide2></slide2></slide>
    <slide :prev="prev" :current="current" :index="2"><slide3></slide3></slide>
  </div>
</template>

<script>
import Slide from './components/Slide';
import Slide1 from './components/Slide1';
import Slide2 from './components/Slide2';
import Slide3 from './components/Slide3';

export default {
  data() {
    return {
      prev: -1,
      current: 0
    };
  },
  ready() {
    document.addEventListener('keydown', (event) => {
      if (event.keyCode === 39) { // right
        this.prev = this.current;
        this.current += 1;
      } else if (event.keyCode === 37) { // left
        if (this.current > 0) {
          this.prev = this.current;
          this.current -= 1;
        }
      }
    });
  },
  components: {
    Slide,
    Slide1,
    Slide2,
    Slide3
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

blockquote {
  font-size: 3rem;
  width: 80rem;
  margin: 15rem auto 0;
  color: #757575;
  p:last-child {
    text-align: right;
    font-size: 3.5rem;
  }
}

.app {
  height: 100vh;
  width: 100vw;
  position: relative;
  overflow: hidden;
}
</style>
