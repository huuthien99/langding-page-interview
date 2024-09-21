<template>
  <div class="content-wrap">
    <h3 class="title">We’re Getting Ready</h3>
    <div class="count-down">
      <CountDown targetDate="2024-10-19T00:00:00"></CountDown>
    </div>
    <div class="group">
      <p class="description">
        We will back to something amazing. Getting the latest updates about our
        games. Please sign up to our newsletter.
      </p>
      <Input>
        <div
          style="
            cursor: pointer;
            display: flex;
            align-items: center;
            height: 100%;
          "
          @click="handleClick"
        >
          <ArrowRight></ArrowRight>
        </div>
      </Input>
    </div>
  </div>
</template>

<script setup>
import CountDown from "../CountDown.vue";
import Input from "../common/Input.vue";
import ArrowRight from "../../assets/icon/ArrowRight.vue";

const handleClick = () => {
  console.log("click send");
};
</script>

<style lang="css" scoped>
@media (min-width: 1366px) {
  .content-wrap {
    max-width: 860px;
    text-align: center;
    background: radial-gradient(
      27.72% 27.79% at 50.81% 68.15%,
      #210544 0%,
      rgba(23, 5, 68, 0.71) 50.52%,
      rgba(23, 5, 68, 0) 100%
    );
    position: absolute;
    top: 32%;
    left: 32%;
    z-index: 1;
    transition: transform 0.2s ease;
  }

  .title {
    color: #ffffff;
    font-family: "Playfair Display" sans-serif;
    font-size: 80px;
    font-weight: 900;
    padding-bottom: 20px;
    line-height: 120px;
  }

  .group {
    width: 560px;
    padding-top: 79px;
    position: relative;
    z-index: 1;
    margin: 0 auto;
  }

  .description {
    color: #ffffff;
    font-style: italic;
    font-size: 18px;
    line-height: 22.68px;
    padding-bottom: 32px;
  }
  .count-down {
    width: 756px;
    height: 140px;
  }
}
@media (min-width: 357px) and (max-width: 1365px) {
  .content-wrap {
    position: absolute;
    top: 140px;
    padding: 0 16px;
    left: 0;
    right: 0;
    background: radial-gradient(
      27.72% 27.79% at 50.81% 68.15%,
      #210544 0%,
      rgba(23, 5, 68, 0.71) 50.52%,
      rgba(23, 5, 68, 0) 100%
    );
  }

  .title {
    font-family: "Playfair Display";
    font-size: 40px;
    font-weight: 900;
    line-height: 50px;
    letter-spacing: 0.6000000238418579px;
    text-align: center;
    color: #ffffff;
    padding-bottom: 38px;
  }

  .count-down {
    max-width: 100%;
    height: 118px;
    width: 100%;
    display: flex;
    align-items: center;
    object-fit: cover;
    padding-bottom: 40px;
  }

  .description {
    font-family: "Montserrat";
    font-size: 12px;
    font-weight: 400;
    line-height: 15px;
    letter-spacing: 0.8999999761581421px;
    text-align: center;
    color: #ffffff;
    padding-bottom: 16px;
  }
}
</style>
