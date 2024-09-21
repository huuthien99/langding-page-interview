<template>
  <div class="partners-container">
    <h2 class="partner-title">Our Partners</h2>
    <Slider></Slider>
  </div>
</template>

<script setup>
import { ref } from "vue";
import Rectangle1 from "../../assets/Rectangle1.png";
import Rectangle2 from "../../assets/Rectangle2.png";
import Rectangle3 from "../../assets/Rectangle3.png";
import Rectangle4 from "../../assets/Rectangle4.png";
import Rectangle5 from "../../assets/Rectangle5.png";
import Slider from "./Slider.vue";

const listPartner = ref([
  {
    id: 1,
    icon: Rectangle1,
  },
  {
    id: 2,
    icon: Rectangle2,
  },
  {
    id: 3,
    icon: Rectangle3,
  },
  {
    id: 4,
    icon: Rectangle4,
  },
  {
    id: 5,
    icon: Rectangle5,
  },
]);
</script>

<style lang="css" scoped>
@media (min-width: 1366px) {
  .partners-container {
    margin-top: 128px;
    background-color: #f6f6f6;
    padding: 120px 230px;
  }

  .partner-title {
    font-family: "Playfair Display";
    font-size: 60px;
    font-weight: 900;
    line-height: 80px;
    letter-spacing: 3.6px;
    text-align: center;
    padding-bottom: 80px;
  }
}
@media (min-width: 375px) and (max-width: 1365px) {
  .partners-container {
    background: #f6f6f6;
    margin-top: 48px;
    padding: 40px 16px;
    text-align: center;
  }
  .partner-title {
    font-family: "Playfair Display";
    font-size: 40px;
    font-weight: 900;
    line-height: 50px;
    padding-bottom: 40px;
    line-height: 50px;
    letter-spacing: 0.6000000238418579px;
  }
}
</style>
