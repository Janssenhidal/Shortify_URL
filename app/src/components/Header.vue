<template>
  <header>
    <div class="logo-text">
      <a href="#">
        <img src="../assets/images/logo.svg" alt="" />
      </a>
      <button
        :class="{ active: showMenu }"
        @click="showMenu = !showMenu"
        class="hamburger hamburger--spin"
        type="button"
      >
        <span class="hamburger-box">
          <span class="hamburger-inner"></span>
        </span>
      </button>
    </div>
    <div :style="showMenu ? 'display:flex' : 'display:hidden'" class="menu">
      <ul>
        <li><a href="#">Features</a></li>
        <li><a href="#">Pricing</a></li>
        <li><a href="#">Resources</a></li>
      </ul>
      <ul>
        <li><a href="#">Login</a></li>
        <li class="signup-li"><a class="signup" href="#">Sign Up</a></li>
      </ul>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",
  props: {},
  data() {
    return {
      showMenu: false,
      show: "block",
    };
  },
  methods: {
    openMenu() {
      console.log("menu");
    },
  },
};
</script>

<style scoped lang="scss">
@import "../assets/styles/hamburger.css";
.color {
  color: red;
}
header {
  display: flex;
  width: 80%;
  margin-left: auto;
  margin-right: auto;
  padding-top: 2rem;
}
button {
  display: none;
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
.menu {
  display: flex;
  flex: 1;
  justify-content: space-between;
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

@media only screen and (max-width: 845px) {
  header {
    display: block;
  }
  ul {
    display: flex;
    flex-direction: column;
    text-align: center;
  }
  .menu {
    display: none;
    flex-direction: column;
    background-color: hsl(257, 27%, 26%);
    border-radius: 1rem;

    li {
      padding-top: 2rem;
      padding-left: 0rem;
    }
    .signup-li {
      padding-bottom: 2rem;
    }
    a {
      color: #fff;
      font-size: 1rem;
      font-weight: 700;
    }

    .signup {
      padding: 0.5rem 3rem;
    }
  }
  button {
    display: block;
    padding: 0;
  }

  .logo-text {
    display: flex;
    justify-content: space-between;
    padding-bottom: 1rem;
  }
}
</style>
