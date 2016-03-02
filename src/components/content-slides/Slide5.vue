<template>
  <h3 class="slide__title">Usage of pseudo elements</h3>
  <p class="big email">daiwei@spanishdict.com</p>
  <p class="big attribute" data-show="I want to show you ">something</p>
  <a class="fancy-link">Fancy</a>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.email::before {
  content: 'Email: ';
}
.attribute::before {
  content: attr(data-show);
}
.fancy-link {
  display: block;
  font-size: 2rem;
  width: 100px;
  height: 50px;
  line-height: 50px;
  text-align: center;
  position: relative;
  cursor: pointer;
  &::after {
    position: absolute;
    content: '';
    display: block;
    height: 0;
    bottom: 0;
    left: 0;
    width: 100%;
    background-color: #FF0066;
    transition: all 1000ms ease;
    z-index: -1;
  }
  &:hover {
    &::after {
      height: 100%;
    }
  }
}
</style>
