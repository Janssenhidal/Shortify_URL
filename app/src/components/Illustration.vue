<template>
  <section class="illustration">
    <div class="illustrate-text">
      <h1>More than just shorter links</h1>
      <p>
        Build your brand’s recognition and get detailed insights on how your
        links are performing.
      </p>
      <a href="#" class="get-started">Get Started</a>
    </div>
    <div class="image">
      <img src="../assets/images/illustration-working.svg" alt="" />
    </div>
  </section>
</template>

<script>
export default {
  name: "Illustration",
};
</script>

<style lang="scss" scoped>
.illustration {
  display: grid;
  grid-template-columns: 1fr 1fr;
  margin-top: 2rem;
  margin-bottom: 12rem;
  .illustrate-text {
    width: 80%;
    margin-left: auto;
  }
  h1 {
    font-size: 4.5rem;
    color: hsl(255, 11%, 22%);
    max-width: 15ch;
    line-height: 5.5rem;
    margin-top: 4rem;
  }
  p {
    color: hsl(257, 7%, 63%);
    padding-top: 0.75rem;
    padding-bottom: 2rem;
    max-width: 40ch;
    font-size: 1.25rem;
  }
  a {
    text-decoration: none;
    color: #fff;
    background-color: hsl(180, 66%, 49%);
    padding: 0.75rem 2rem;
    border-radius: 1.5rem;
    font-weight: 700;

    &:hover {
      opacity: 0.6;
    }
  }
  .image {
    position: relative;

    img {
      position: absolute;
      top: 0;
      left: 80px;
      height: auto;
      max-width: 100%;
    }
  }
}
</style>
