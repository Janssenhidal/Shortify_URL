<template>
  <div @mouseenter="isHover = true" @mouseleave="isHover = false" class="links">
    <span v-if="isHover" @click="test">x</span>
    <p class="longLink">{{ longLink }}</p>
    <div class="line"></div>
    <hr />
    <div class="copySide">
      <p class="shortLink">{{ shortLink }}</p>
      <Button @btn-click="toggleCopy" :text="text" :color="color" />
      <input ref="dummyInput" type="hidden" :value="value" />
    </div>
  </div>
</template>

<script>
import Button from "./Button.vue";
export default {
  name: "LinkBar",
  components: {
    Button,
  },
  props: {
    shortLink: String,
    longLink: String,
    value: String,
    dummyInput: String,
  },
  data() {
    return {
      text: "Copy",
      color: "hsl(180, 66%, 49%)",
      copied: Boolean,
      isHover: false,
    };
  },
  methods: {
    test() {
      console.log("delete");
    },
    toggleCopy() {
      this.text = "Copied!";
      this.color = "hsl(257, 27%, 26%)";
      setTimeout(() => {
        this.text = "Copy";
        this.color = "hsl(180, 66%, 49%)";
      }, 2000);
      this.copied = !this.copied;

      this.$refs.dummyInput.type = "text";
      this.$refs.dummyInput.select();
      // this.$refs.dummyInput.setSelectionRange(0, 99999);
      document.execCommand("copy");
      this.$refs.dummyInput.type = "hidden";
    },
  },
};
</script>

<style lang="scss" scoped>
.links {
  position: relative;
  padding-top: 0.2rem;
  background-color: #fff;
  width: 60%;
  margin-left: auto;
  margin-right: auto;
  border-radius: 0.25rem;
  display: flex;
  justify-content: space-between;
  height: auto;
  align-items: center;
  margin-bottom: 1rem;
  padding: 1rem 0rem;

  .copySide {
    display: flex;
    align-items: center;
    gap: 1rem;
  }

  p {
    font-size: 0.9rem;
  }

  .longLink {
    padding-left: 1rem;
  }
  .shortLink {
    color: hsl(180, 66%, 49%);
  }
}
span {
  position: absolute;
  top: 0px;
  left: 5px;
  color: gray;
  cursor: pointer;
}
hr {
  display: none;
  opacity: 0.3;
}

@media only screen and (max-width: 1220px) {
  .links {
    width: 70%;
  }
}

@media only screen and (max-width: 1000px) {
  .links {
    padding: 1rem;
    display: grid;
    grid-auto-columns: 1fr;
    width: 80%;
    .longLink {
      padding-left: 0rem;
    }
    .copySide {
      display: grid;
      grid-auto-columns: 1fr;
      gap: 0.5rem;
    }
  }
  hr {
    display: block;
    opacity: 0.3;
    margin: 0.3rem 0rem;
  }
}

@media only screen and (max-width: 450px) {
  .links {
    width: 90%;

    p {
      font-size: 0.8rem;
    }
  }
}
</style>
