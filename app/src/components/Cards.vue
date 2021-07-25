<template>
  <section class="statistics">
    <InputPanel />
    <div class="advanced">
      <shortenBar />
      <h2>Advanced Statistics</h2>
      <p>
        Track how your links are performing across the web with our advanced
        statistics dashboard.
      </p>
    </div>
    <div class="panels-grid">
      <div class="panels first">
        <img src="../assets/images/icon-brand-recognition.svg" alt="" />
        <h3>Brand Recognition</h3>
        <p>
          Boost your brand recognition with each click. Generic links don’t mean
          a thing. Branded links help instil confidence in your content.
        </p>
      </div>
      <div class="panels second">
        <img src="../assets/images/icon-detailed-records.svg" alt="" />
        <h3>Detailed Records</h3>
        <p>
          Gain insights into who is clicking your links. Knowing when and where
          people engage with your content helps inform better decisions.
        </p>
      </div>
      <div class="panels third">
        <img src="../assets/images/icon-fully-customizable.svg" alt="" />
        <h3>Fully Customizable</h3>
        <p>
          Improve brand awareness and content discoverability through
          customizable links, supercharging audience engagement.
        </p>
      </div>
    </div>
  </section>
</template>

<script>
import InputPanel from "./InputPanel.vue";
export default {
  name: "Cards",
  components: {
    InputPanel,
  },
};
</script>

<style lang="scss" scoped>
.statistics {
  background-color: hsl(0, 5%, 92%);
  margin-top: 5rem;
  position: relative;
  .advanced {
    text-align: center;
    padding-top: 5rem;
    h2 {
      font-size: 2rem;
      color: hsl(255, 11%, 22%);
    }
    p {
      margin-top: 1rem;
      color: hsl(257, 7%, 63%);
      max-width: 45ch;
      margin-left: auto;
      margin-right: auto;
    }
  }

  .panels-grid {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    width: 80%;
    margin-left: auto;
    margin-right: auto;
    gap: 2.5rem;
    &::after {
      content: "";
      position: absolute;
      z-index: 1;
      width: 80%;
      height: 10px;
      background: hsl(180, 66%, 49%);
      top: 455px;
    }
  }
  .panels {
    position: relative;
    margin-top: 4rem;
    background-color: #fff;
    border-radius: 0.5rem;
    margin-bottom: 12rem;
    z-index: 5;
    h3 {
      color: hsl(255, 11%, 22%);
      padding-top: 3rem;
      padding-left: 2rem;
      font-size: 1.3rem;
    }
    p {
      color: hsl(257, 7%, 63%);
      padding: 2rem;
      font-size: 0.9rem;
    }
    img {
      position: absolute;
      left: 2rem;
      top: -2rem;
      background-color: hsl(257, 27%, 26%);
      padding: 1rem;
      border-radius: 50%;
    }
  }

  .second {
    top: 3rem;
  }
  .third {
    top: 6rem;
  }
}
</style>
