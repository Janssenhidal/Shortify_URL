<template>
  <section class="illustration">
    <div class="illustrate-text">
      <h1>More than just shorter links</h1>
      <p>
        Build your brand’s recognition and get detailed insights on how your
        links are performing.
      </p>
      <p><a href="#" class="get-started">Get Started</a></p>
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
  margin-bottom: 6rem;
  .illustrate-text {
    display: flex;
    flex-direction: column;
    width: 80%;
    margin-left: auto;
    justify-content: center;
  }
  h1 {
    font-size: 4.5rem;
    color: hsl(255, 11%, 22%);
    max-width: 15ch;
    line-height: 5.5rem;
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
}
.image {
  overflow-y: hidden;
  overflow-x: hidden;
  img {
    width: 100%;
    transform: translateX(6%);
  }
}
@media only screen and (max-width: 1100px) {
  .illustrate-text {
    h1 {
      font-size: 3.5rem;
      line-height: 4rem;
    }
    p {
      font-size: 1rem;
    }
  }
}
@media only screen and (max-width: 845px) {
  .illustration {
    grid-template-columns: 1fr;
    text-align: center;
  }
  .illustrate-text {
    width: 100%;
    margin: auto;
    position: relative;
    h1 {
      font-size: 3rem;
      line-height: 3.5rem;
      margin-top: 0rem;
    }
    p {
      font-size: 1rem;
      margin: auto;
    }
  }
  .image {
    img {
      width: 80%;
      transform: translateX(12%);
    }
  }
}

@media only screen and (max-width: 415px) {
  .illustrate-text {
    h1 {
      font-size: 2.2rem;
      line-height: 2.5rem;
    }
    p {
      font-size: 0.9rem;
    }
  }
}
</style>
