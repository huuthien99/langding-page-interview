<template>
  <FooterInfo></FooterInfo>
  <div class="footer-container">
    <p>2017 Copyright. Policy.</p>
  </div>
</template>

<script setup>
import FooterInfo from "./FooterInfo.vue";
</script>

<style lang="css" scoped>
@media (min-width: 1366px) {
  .footer-container {
    height: 80px;
  }
  p {
    line-height: 80px;
  }
}

@media (min-width: 375px) and (max-width: 1365px) {
  .footer-container {
    height: 86px;
  }
  p {
    line-height: 86px;
  }
}

.footer-container {
  width: 100%;
  background: #000000;
}

p {
  font-size: 18px;
  font-family: "Montserrat";
  text-align: center;
  font-weight: 400;
  color: #ffffff;
}
</style>
