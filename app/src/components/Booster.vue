<template>
  <section class="boost">
    <h1>Boost your links today</h1>
    <a href="#">Get Started</a>
  </section>
</template>

<script>
export default {
  name: "Booster",
};
</script>

<style lang="scss" scoped>
.boost {
  text-align: center;
  background-image: url("../assets/images/bg-boost-desktop.svg");
  background-repeat: no-repeat;
  background-size: cover;
  background-color: hsl(257, 27%, 26%);
  height: auto;
}
h1 {
  color: #fff;
  font-size: 2rem;
  padding-top: 3rem;
  padding-bottom: 2rem;
}
a {
  display: inline-block;
  text-decoration: none;
  color: #fff;
  background-color: hsl(180, 66%, 49%);
  padding: 0.75rem 2rem;
  border-radius: 1.5rem;
  font-weight: 700;
  margin-bottom: 3rem;
  &:hover {
    opacity: 0.8;
  }
}
@media only screen and (max-width: 500px) {
  h1 {
    font-size: 1.5rem;
  }
}
</style>
