<template>
  <div class="link-panels">
    <div class="links">
      <p class="longLink">{{ longLink }}</p>
      <div class="copySide">
        <p class="shortLink">{{ shortLink }}</p>
        <Button @btn-click="toggleCopy" :text="text" :color="color" />
      </div>
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
  },
  data() {
    return {
      text: "Copy",
      color: "hsl(180, 66%, 49%)",
      copied: Boolean,
    };
  },
  methods: {
    toggleCopy() {
      this.text = "Copied!";
      this.color = "hsl(257, 27%, 26%)";
      setTimeout(() => {
        this.text = "Copy";
        this.color = "hsl(180, 66%, 49%)";
      }, 2000);
      this.copied = !this.copied;
    },
  },
};
</script>

<style lang="scss" scoped>
.link-panels {
  padding-top: 0.2rem;
}
.links {
  background-color: #fff;
  width: 60%;
  margin-left: auto;
  margin-right: auto;
  border-radius: 0.25rem;
  display: flex;
  justify-content: space-between;
  height: 50px;
  align-items: center;
  margin-bottom: 1rem;
  padding: 1.8rem 0rem;

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
</style>
