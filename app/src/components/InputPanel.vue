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
export default {
  name: "InputPanel",
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
  height: 150px;
  border-radius: 0.5rem;
}
.input-text {
  width: 75%;
  margin-left: auto;
  margin-right: auto;
  margin-left: 2rem;
}
input {
  height: 50px;
  width: 100%;
  margin-right: 1rem;
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
  margin-right: 2rem;
  padding: 0.75rem 1.5rem;
  width: 9rem;
  height: 3rem;
  border-radius: 0.5rem;
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
  padding-top: 2.7rem;
  text-align: center;
  display: flex;
  gap: 0.5rem;
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
</style>
