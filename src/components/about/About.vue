<template>
  <div class="about-wrap">
    <div class="content">
      <h2 class="about-us-title">About Us</h2>
      <p class="info-content__description about-text">
        Browse our selection of free online games and have a great time without
        leaving the site! Our Kids Games option also includes game reviews,
        extensive game cheats and walkthroughs, and much more. We have exclusive
        free downloads, videos, and articles as well. Etech reviews the most
        popular kids games from all the most popular video gaming platforms, so
        you don’t need to search around for fun anywhere else on the Internet.
        Explore a whole new world of gaming on Etech.
      </p>
      <div class="mobile-count">
        <div class="total-user">
          <p class="total-count">600<span>M</span>+</p>
          <p class="name-count">Users</p>
        </div>
        <div class="total-game">
          <p class="total-count">135+</p>
          <p class="name-count">Games</p>
        </div>
      </div>
    </div>
    <div class="content">
      <div v-for="(item, index) in dataInfo" :key="index" class="info-item">
        <div class="icon">
          <component :is="item.icon" />
        </div>
        <div class="info-content">
          <p class="info-content__title">{{ item.title }}</p>
          <p class="info-content__description">{{ item.description }}</p>
        </div>
      </div>
    </div>
  </div>
  <div class="witch">
    <img src="../../assets/Illustrator.png" alt="phu thuy" class="img-witch" />
  </div>
  <div class="pin-map">
    <img src="../../assets/Pin-map.png" alt="map" class="img-pin-map" />
  </div>
</template>

<script setup>
import { ref } from "vue";
import DateTime from "../../assets/icon/DateTime.vue";
import Design from "../../assets/icon/Design.vue";
import Team from "../../assets/icon/Team.vue";

const dataInfo = ref([
  {
    title: "24 - Hour",
    description:
      "24/7 access ensures operators' businesses runs smoothly all year long.",
    icon: DateTime,
  },
  {
    title: "Design",
    description:
      "Combining imaginative universes, play dynamics, and unprecedented gameplay, our games transcend the boundaries of the virtual world by weaving innovative gameplay.",
    icon: Design,
  },
  {
    title: "Team",
    description:
      "Etech is an award-winning, international studio of designers, artists, animators and producers that create content for the biggest names in film and video games. ",
    icon: Team,
  },
]);
</script>

<style lang="css" scoped>
.about-us-title {
  font-size: 60px;
  font-weight: 900;
  line-height: 60px;
  padding-bottom: 40px;
}

.info-content__description {
  font-weight: 400;
  color: #757575;
  font-family: "Montserrat";
  line-height: 19.6px;
}

.icon {
  width: 50px;
  min-width: 50px;
  height: 50px;
  border-radius: 50%;
  background-color: #e3fcff;
  display: flex;
  align-items: center;
  justify-content: center;
}

@media (min-width: 1366px) {
  .about-wrap {
    display: flex;
    gap: 40px;
    justify-content: center;
    font-family: "Montserrat";
    padding-bottom: 68px;
  }
  .content {
    width: calc(560px - (75px * 2));
  }

  .content:last-child {
    background: #eeeeee;
    padding: 113px 75px;
  }

  .total-user {
    padding-bottom: 39px;
  }

  .about-text {
    padding-bottom: 79px;
  }
  .total-count {
    font-weight: 700;
    font-size: 80px;
    color: #079bee;
    padding-bottom: 4px;
  }
  .name-count {
    font-weight: 700;
    font-size: 24px;
    line-height: 30px;
  }
  span {
    font-size: 40px;
  }
  .info-item {
    display: flex;
    gap: 24px;
  }

  .info-item:not(:last-child) {
    padding-bottom: 40px;
  }
  .info-content {
    display: flex;
    gap: 8px;
    flex-direction: column;
  }
  .info-content__title {
    font-size: 24px;
    line-height: 30px;
    font-weight: 700;
    font-family: "Montserrat";
  }
  .pin-map {
    width: 1160px;
    height: 428px;
    margin: 0 auto;
    margin-bottom: 128px;
  }

  .witch {
    width: 533px;
    height: 437px;
    margin: 0 auto;
    position: relative;
    z-index: 1;
    top: 96px;
    left: 20px;
    animation: fly 5s infinite linear;
  }
}
@media (min-width: 357px) and (max-width: 1365px) {
  .about-wrap {
    flex-direction: column;
    justify-content: center;
  }

  .about-us-title {
    padding-bottom: 16px;
    padding-left: 16px;
    padding-right: 16px;
  }

  .info-content__description:not(:last-child) {
    padding-bottom: 40px;
  }

  .mobile-count {
    display: flex;
    gap: 16px;
    justify-content: center;
    padding-bottom: 40px;
    padding-left: 16px;
    padding-right: 16px;
  }

  .about-text {
    padding-left: 16px;
    padding-right: 16px;
  }

  .total-user,
  .total-game {
    min-width: 164px;
  }

  .total-count {
    font-family: "Montserrat";
    font-size: 44px;
    font-weight: 700;
    line-height: 53.64px;
    letter-spacing: -1px;
    text-align: left;
    color: #079bee;
  }
  span {
    font-family: "Montserrat";
    font-size: 20px;
    font-weight: 700;
    line-height: 24.38px;
    letter-spacing: -1px;
    text-align: left;
  }
  .name-count {
    font-family: "Montserrat";
    font-size: 24px;
    font-weight: 700;
    line-height: 30px;
    text-align: left;
  }
  .content:last-child {
    background: #eeeeee;
    padding: 40px 16px;
  }

  .info-item {
    display: flex;
    gap: 20px;
  }

  .info-content__title {
    font-family: "Montserrat";
    font-size: 24px;
    font-weight: 700;
    line-height: 30px;
    text-align: left;
  }

  .info-content {
    display: flex;
    flex-direction: column;
    gap: 12px;
  }

  .pin-map {
    width: 375px;
    height: 146.27px;
    margin: 0 auto;
  }
  .img-pin-map {
    object-fit: cover;
    width: 375px;
    height: 146.27px;
  }

  .witch {
    margin: 0 auto;
    position: relative;
    z-index: 1;
    top: 30px;
    left: 20px;
    width: 300px;
    height: 243px;
    animation: fly 5s infinite linear;
    margin-bottom: 48px;
  }
  .img-witch {
    width: 300px;
    height: 243px;
  }
}

@keyframes fly {
  0% {
    right: 0;
  }
  50% {
    right: 200px;
    transform: rotate(10deg);
  }
  100% {
    right: 0;
    transform: rotate(0deg);
  }
}
</style>
