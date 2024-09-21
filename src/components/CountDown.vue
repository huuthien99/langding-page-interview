<template>
  <div class="countdown">
    <div class="time-box">
      <span>{{ days }}</span>
      <p>Days</p>
    </div>
    <span>:</span>
    <div class="time-box">
      <span>{{ hours }}</span>
      <p>Hours</p>
    </div>
    <span>:</span>
    <div class="time-box">
      <span>{{ minutes }}</span>
      <p>Minutes</p>
    </div>
    <span>:</span>
    <div class="time-box">
      <span>{{ seconds }}</span>
      <p>Second</p>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from "vue";
const { targetDate } = defineProps({
  targetDate: {
    type: String,
  },
});
const days = ref(0);
const hours = ref(0);
const minutes = ref(0);
const seconds = ref(0);
let timer = null;

const calculateTimeLeft = () => {
  const target = new Date(targetDate).getTime();
  const now = new Date().getTime();
  const difference = target - now;
  const millisecondsInOneDay = 1000 * 60 * 60 * 24;
  const millisecondsInOneMinus = 1000 * 60 * 60;

  if (difference > 0) {
    days.value = Math.floor(difference / millisecondsInOneDay);
    hours.value = Math.floor(
      (difference % millisecondsInOneDay) / millisecondsInOneMinus
    );

    minutes.value = Math.floor(
      (difference % millisecondsInOneMinus) / (1000 * 60)
    );
    seconds.value = Math.floor((difference % (1000 * 60)) / 1000);
  } else {
    clearInterval(timer);
  }
};

onMounted(() => {
  calculateTimeLeft();
  timer = setInterval(calculateTimeLeft, 1000);
});

onUnmounted(() => {
  if (timer) {
    clearInterval(timer);
  }
});
</script>

<style scoped>
@media (min-width: 1366px) {
  .countdown {
    box-shadow: 0px 4px 10px 0px #00000040;
    background-color: #ffffff;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 21px;
    width: 100%;
    height: 100%;
    gap: 52px;
  }

  .time-box {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin: 0 5px;
  }

  span {
    font-size: 60px;
    font-weight: 900;
    font-family: "Playfair Display";
  }

  p {
    margin: 0;
    font-family: "Montserrat";
    font-weight: 700;
    font-size: 16px;
  }
}
@media (min-width: 357px) and (max-width: 1365px) {
  .countdown {
    width: 100%;
    height: 100%;
    gap: 4px;
    border-radius: 21px;
    background-color: #ffffff;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .time-box {
    display: flex;
    flex-direction: column;
    align-items: center;
    min-width: 54px;
  }
  span {
    font-family: "Playfair Display";
    font-size: 36px;
    font-weight: 900;
    line-height: 45px;
  }

  p {
    font-family: "Montserrat";
    font-size: 12px;
    font-weight: 700;
    line-height: 14.63px;
    letter-spacing: -0.651724100112915px;
  }
}
</style>
