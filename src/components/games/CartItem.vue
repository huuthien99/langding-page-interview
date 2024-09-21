<template>
  <div class="cart-item-container">
    <img v-if="data?.thumbnail" :src="data?.thumbnail" :alt="data?.name" />
    <img v-else src="@/assets/img.png" :alt="data?.name" />
    <div class="content-image">
      <h4 class="name-game">{{ data?.name }}</h4>
      <p class="description-game">{{ data?.description }}</p>
    </div>
  </div>
</template>

<script setup>
defineProps({
  data: Object,
});
</script>

<style lang="css" scoped>
.cart-item-container {
  position: relative;
  border-radius: 20px;
  overflow: hidden;
  transition: transform 0.2s ease;
}

img {
  border-radius: 20px;
  object-fit: cover;
  box-shadow: 0px 4px 10px 0px #00000040;
  background-position: center;
}

.content-image {
  position: absolute;
  z-index: 1;
  bottom: 0;
  padding: 0 32px 40px 32px;
  overflow: hidden;
}

.name-game {
  color: #ffffff;
  font-family: "Montserrat";
  font-weight: 700;
  font-size: 48px;
  padding-bottom: 15px;
  line-height: 60px;
  letter-spacing: -1px;
}

.description-game {
  color: #ffffff;
  font-family: "Montserrat";
  font-weight: 400;
  font-style: italic;
  line-height: 19.6px;
}
</style>
