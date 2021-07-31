<template>
  <button @click="onClick" :style="{ background: color }">
    {{ text }}
  </button>
</template>

<script>
export default {
  name: "Button",
  props: {
    text: String,
    color: String,
  },
  methods: {
    onClick() {
      this.$emit("btn-click");
    },
  },
};
</script>

<style lang="scss" scoped>
button {
  border: 0;
  outline: 0;
  cursor: pointer;
  padding: 0.3rem 1rem;
  margin-right: 1rem;
  border-radius: 0.25rem;
  font-size: 0.8rem;
  color: #fff;
}

@media only screen and (max-width: 1000px) {
  button {
    margin: 0;
  }
}
</style>
