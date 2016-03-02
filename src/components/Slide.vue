<template>
  <div class="slide" v-show="show" transition="switch-slides">
    <slot>
  </div>
</template>

<script>
import Vue from 'vue';

export default {
  props: {
    prev: {
      type: Number,
      required: true
    },
    current: {
      type: Number,
      required: true
    },
    index: {
      type: Number,
      required: true
    }
  },
  computed: {
    show() {
      return this.current === this.index;
    }
  }
};

Vue.transition('switch-slides', {
  css: false,
  enter(el, done) {
    el.style.opacity = '0';
    if (this.prev < this.current) {
      el.style.transform = `translateX(${10}vw)`;
    } else {
      el.style.transform = `translateX(${-10}vw)`;
    }
    requestAnimationFrame(() => {
      el.style.opacity = '1';
      el.style.transform = `translateX(0)`;
    });
    el.addEventListener('transitionend', function transitionend() {
      el.removeEventListener('transitionend', transitionend);
      done();
    });
  },
  leave(el, done) {
    el.style.opacity = '1';
    if (this.prev < this.current) {
      el.style.transform = `translateX(${-10}vw)`;
    } else {
      el.style.transform = `translateX(${10}vw)`;
    }
    requestAnimationFrame(() => {
      el.style.opacity = '0';
    });
    el.addEventListener('transitionend', function transitionend() {
      el.removeEventListener('transitionend', transitionend);
      done();
    });
  }
});
</script>

<style lang="scss">
.slide {
  --border-color: #0097A7;
  --background-color: #FEF5E7;
  height: 100vh;
  width: 100vw;
  border: 20px solid var(--border-color);
  background-color: var(--background-color);
  position: absolute;
  top: 0;
  left: 0;
  transition: opacity 200ms ease, transform 200ms ease;
}

.slide__header {
  position: relative;
  top: 50%;
  transform: translateY(-50%);
  text-align: center;
  font-size: 10rem;
}
</style>
