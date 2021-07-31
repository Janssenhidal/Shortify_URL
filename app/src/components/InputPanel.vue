<template>
  <div class="shorten-panel">
    <div class="container">
      <div class="input-text">
        <input
          ref="button"
          v-model="url"
          v-bind:class="{ placeholder: error }"
          type="text"
          placeholder="Shorten a link here..."
          @keypress.enter="shorten"
        />
        <p v-show="error" ref="error" class="error">Please add a link</p>
      </div>

      <button type="submit" v-on:click="shorten">
        <span v-if="!isLoading">Shorten It!</span>
        <img
          class="loading"
          v-if="isLoading"
          src="../assets/images/circle_loading.gif"
          alt=""
        />
      </button>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "InputPanel",
  data() {
    return {
      url: null,
      error: false,
      isLoading: false,
    };
  },
  methods: {
    async shorten() {
      if (this.url === null) {
        this.error = true;
        this.$refs.button.style.border = "2px solid hsl(0, 87%, 67%)";
      } else {
        console.log("Fetching API");
        this.isLoading = true;
        await axios
          .get(`https://api.shrtco.de/v2/shorten?url=${this.url}`)
          .then((response) => {
            this.isLoading = false;
            this.url = null;
            const allLinks = {
              originalLink: response.data.result.original_link,
              shortLink: response.data.result.full_short_link,
            };
            this.$emit("add-link", allLinks);
          })
          .catch((error) => {
            console.log(error);
          });
      }
    },
  },
};
</script>

<style lang="scss" scoped>
.shorten-panel {
  position: absolute;
  top: -80px;
  left: 50%;
  transform: translateX(-50%);
  width: 60%;
  margin-left: auto;
  margin-right: auto;

  background-image: url("../assets/images/bg-shorten-desktop.svg");
  background-repeat: no-repeat;
  background-size: cover;
  background-color: hsl(257, 27%, 26%);

  height: auto;
  border-radius: 0.5rem;
}
.input-text {
  width: 75%;
  margin-left: 2rem;
}
input {
  height: 50px;
  width: 100%;
  border-radius: 0.5rem;
  border: none;
  padding-left: 2rem;
  color: hsl(255, 11%, 22%);
  &::placeholder {
    opacity: 0.6;
  }
}
button {
  background-color: hsl(180, 66%, 49%);
  padding: 0.75rem 1.5rem;
  border-radius: 0.5rem;
  margin-right: 2rem;
  width: 9rem;
  height: 3rem;
  border: none;
  color: #fff;
  font-weight: 700;
  cursor: pointer;
  &:hover {
    background-color: hsl(180, 66%, 80%);
  }

  .loading {
    width: 30px;
    height: 30px;
  }
}
.container {
  text-align: center;
  display: flex;
  gap: 0.5rem;
  padding: 2rem 0rem;
  justify-content: center;
  align-items: center;
}

.error {
  text-align: left;
  color: hsl(0, 87%, 67%);
  font-style: italic;
  padding-top: 0.5rem;
  font-size: 0.8rem;
}
.placeholder {
  &::placeholder {
    color: hsl(0, 87%, 67%);
    opacity: 0.6;
  }
}
@media only screen and (max-width: 1220px) {
  .shorten-panel {
    width: 70%;
    height: auto;
  }
}
@media only screen and (max-width: 1000px) {
  .shorten-panel {
    width: 80%;
  }
  .container {
    display: flex;
    align-items: center;
    flex-direction: column;
    padding: 0rem;
    padding-top: 1.5rem;
  }
  button {
    margin-right: 0rem;
    width: 85%;
    margin-bottom: 1.5rem;
    margin-top: 1rem;
  }
  .input-text {
    width: 85%;
    margin-left: 0rem;
  }
}

@media only screen and (max-width: 450px) {
  .shorten-panel {
    width: 90%;
  }
}
</style>
