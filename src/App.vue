<template>
  <div id="app">
    <h1 class="title">Поля ввода компонентов RGB и бегунки:</h1>
    <color @upd_color="update" color="red" />
    <color @upd_color="update" color="green" />
    <color @upd_color="update" color="blue" />
  </div>
</template>

<script>
import color from "./components/color.vue";

export default {
  name: "App",
  components: {
    color,
  },
  data() {
    return {
      red: 255,
      green: 255,
      blue: 255,
    };
  },
  methods: {
    update: function ({ color, value }) {
      this[color] = +value;
      document.body.style.backgroundColor = `rgb(${this.red}, ${this.green}, ${this.blue})`;
      document.querySelector(".title").style.color = `rgb(${255 - this.red}, ${
        255 - this.green
      }, ${255 - this.blue})`;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  width: 400px;
  margin: 100px auto 0 auto;
  text-align: center;
}
input {
  zoom: 150%;
}
</style>
