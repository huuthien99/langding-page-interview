<template>
  <div class="hero-container">
    <Header @onChangeLangue="onChangeLangue"></Header>
    <Content></Content>
    <div class="fairy">
      <img alt="ong tien" src="@/assets/ongtien.png" class="img-fairy" />
    </div>
  </div>
</template>

<script setup>
import Header from "./Header.vue";
import Content from "./Content.vue";
</script>

<style lang="css" scoped>
@media (min-width: 1366px) {
  .hero-container {
    background: url("@/assets/BG.png");
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    height: 988.64px;
    margin-bottom: 128px;
    position: relative;
  }

  .fairy {
    position: absolute;
    top: 85px;
    left: 6px;
    user-select: none;
  }
}

@media (min-width: 357px) and (max-width: 1365px) {
  .hero-container {
    background: url("@/assets/BGMB.png");
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    position: relative;
    height: 724px;
    margin-bottom: 258px;
  }

  .fairy {
    position: absolute;
    width: 342px;
    height: 258px;
    bottom: -178px;
    z-index: 1;
    left: 50%;
    transform: translateX(-33%);
  }
  .img-fairy {
    width: 342px;
    height: 258px;
    object-fit: cover;
  }
}
</style>
