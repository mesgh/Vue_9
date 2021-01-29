<template>
  <div class="color">
    <div class="color__text">{{ color.toUpperCase() }}:</div>
    <input
      class="color__input"
      type="number"
      min="0"
      max="255"
      v-model="value"
    />
    <input type="range" min="0" max="255" v-model="value" />
  </div>
</template>

<script>
export default {
  name: "color",
  props: {
    color: String
  },
  data() {
    return {
      value: 255,
    };
  },
  computed: {},
  watch: {
    value: function () {
      this.$emit("upd_color", {
        color: this.color,
        value: this.value,
      });
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.color__text {
  font-size: 24px;
  text-align: left;
}
.color__input {
  width: 50px;
}
.color {
  display: grid;
  grid-auto-flow: column;
  grid-auto-columns: 1fr;
}
.color:not(:last-child) {
  margin-bottom: 15px;
}
</style>
