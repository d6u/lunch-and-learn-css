<template>
  <h3 class="slide__title">List of elements</h3>
  <p class="centered"><img src="../../assets/flexbox-example-1.jpg" alt=""></p>
  <div class="center-content">
    <button @click="addBox">Add box</button>
  </div>
  <div class="demo-parent centered">
    <div class="demo-box" v-for="box in boxes"></div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num: 0
    };
  },
  computed: {
    boxes() {
      return Array.apply(null, {length: this.num}).map((el, i) => i);
    }
  },
  methods: {
    addBox() {
      this.num += 1;
    }
  }
};
</script>

<style lang="scss" scoped>
.centered {
  width: 800px;
  margin: 0 auto;
}

.center-content {
  text-align: center;
}

.demo-parent {
  background-color: #0097A7;
  width: 800px;
  height: 200px;
}

.demo-box {
  width: 150px;
  height: 150px;
  background-color: #35495E;
  float: left;
}
</style>
