<template>
  <div class="slider-container">
    <Swiper
      ref="mySwiper"
      :slides-per-view="5"
      :space-between="40"
      :breakpoints="{
        375: { slidesPerView: 1, spaceBetween: 12 },
        568: { slidesPerView: 2, spaceBetween: 20 },
        768: { slidesPerView: 3, spaceBetween: 30 },
        1024: { slidesPerView: 4, spaceBetween: 30 },
        1366: { slidesPerView: 5, spaceBetween: 40 },
      }"
      class="mySwiper"
      pagination
      :navigation="{
        nextEl: '.custom-next',
        prevEl: '.custom-prev',
      }"
      @swiper="onSwiper"
    >
      <SwiperSlide v-for="(partner, index) in listPartner" :key="index">
        <img :src="partner.icon" alt="partner" class="partner-logo" />
      </SwiperSlide>
    </Swiper>
    <div @click="goPrev" class="custom-prev">
      <img src="../../assets/icon/ArrowSquareLeft.svg" width="40" height="40" />
    </div>
    <div @click="goNext" class="custom-next">
      <img
        src="../../assets/icon/ArrowSquareRight.svg"
        width="40"
        height="40"
      />
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/swiper-bundle.css";
import Rectangle1 from "../../assets/Rectangle1.png";
import Rectangle2 from "../../assets/Rectangle2.png";
import Rectangle3 from "../../assets/Rectangle3.png";
import Rectangle4 from "../../assets/Rectangle4.png";
import Rectangle5 from "../../assets/Rectangle5.png";

const mySwiper = ref(null);

const listPartner = ref([
  { id: 1, icon: Rectangle1 },
  { id: 2, icon: Rectangle2 },
  { id: 3, icon: Rectangle3 },
  { id: 4, icon: Rectangle4 },
  { id: 5, icon: Rectangle5 },
]);

const onSwiper = (swiper) => {
  mySwiper.value = swiper; // Gán swiper instance
};

const goPrev = () => {
  if (mySwiper.value) {
    mySwiper.value.slidePrev();
  }
};

const goNext = () => {
  if (mySwiper.value) {
    mySwiper.value.slideNext();
  }
};
</script>

<style scoped>
.slider-container {
  position: relative;
  width: 100%;
  margin: auto;
}
.partner-logo {
  max-width: 100%;
  height: auto;
}
@media (min-width: 1366px) {
  .custom-prev,
  .custom-next {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    cursor: pointer;
    z-index: 10;
  }
  .custom-prev {
    left: -30px;
  }
  .custom-next {
    right: -30px;
  }
}
@media (min-width: 357px) and (max-width: 1365px) {
  .custom-prev,
  .custom-next {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    cursor: pointer;
    z-index: 10;
  }
  .custom-prev {
    left: 0;
  }
  .custom-next {
    right: 0px;
  }
}
</style>
