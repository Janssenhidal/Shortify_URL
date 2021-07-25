<template>
  <Header />
  <Illustration />
</template>

<script>
import Header from "./components/Header.vue";
import Illustration from "./components/Illustration.vue";

export default {
  name: "App",
  components: {
    Header,
    Illustration,
  },
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@500;700&display=swap");
* {
  box-sizing: border-box;
  font-family: "poppins";
  font-size: 18px;
  padding: 0;
  margin: 0;
}
</style>
