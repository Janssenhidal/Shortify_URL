<template>
  <header>
    <div class="logo-text">
      <a href="#">
        <img src="../assets/images/logo.svg" alt="" />
      </a>
      <ul>
        <li><a href="#">Features</a></li>
        <li><a href="#">Pricing</a></li>
        <li><a href="#">Resources</a></li>
      </ul>
    </div>
    <ul>
      <li><a href="#">Login</a></li>
      <li><a class="signup" href="#">Sign Up</a></li>
    </ul>
  </header>
</template>

<script>
export default {
  name: "Header",
  props: {},
};
</script>

<style scoped lang="scss">
header {
  display: flex;
  justify-content: space-between;
  width: 80%;
  margin-left: auto;
  margin-right: auto;
  padding-top: 2rem;
}
ul {
  display: flex;
  list-style: none;
}
li {
  padding-left: 2rem;
}
a {
  text-decoration: none;
  color: hsl(257, 7%, 63%);
  font-size: 0.9rem;

  &:hover {
    color: hsl(255, 11%, 22%);
  }
}
.logo-text {
  display: flex;
}

.signup {
  background-color: hsl(180, 66%, 49%);
  padding: 0.5rem 1.25rem;
  border-radius: 1.5rem;
  color: #fff;
  &:hover {
    opacity: 0.6;
    color: #fff;
  }
}
</style>
