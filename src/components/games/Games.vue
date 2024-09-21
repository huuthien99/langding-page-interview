<template>
  <div class="games-container">
    <h2 class="game-title">Our Games</h2>
    <p class="game-description">
      As a pioneer of mobile app gamification, we take pride in originality and
      individuality, providing global players with state-of-the-art games that
      feature splendid storylines, sensational sound effects and magnificent
      animation that never cease to impress.
    </p>
    <div class="list-game">
      <div
        class="game-item"
        :class="{ isChan: (index + 1) % 2 === 0 }"
        v-for="(item, index) in gameList"
        :key="item.id"
      >
        <CartItem :data="item" />
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
import CartItem from "./CartItem.vue";
const gameList = ref([
  {
    id: 1,
    name: "E-Space",
    thumbnail: "",
    description:
      "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
  },
  {
    id: 2,
    name: "Kingland",
    thumbnail: "",
    description:
      "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
  },

  {
    id: 3,
    name: "The Last Game",
    thumbnail: "",
    description:
      "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
  },
  {
    id: 4,
    name: "G-Dragon",
    thumbnail: "",
    description:
      "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
  },
  {
    id: 5,
    name: "Pirates",
    thumbnail: "",
    description:
      "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
  },
  {
    id: 6,
    name: "Witch Party",
    thumbnail: "",
    description:
      "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
  },
  {
    id: 7,
    name: "Rocky",
    thumbnail: "",
    description:
      "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
  },
  {
    id: 8,
    name: "Blue Fire",
    thumbnail: "",
    description:
      "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
  },
  {
    id: 9,
    name: "Witch Party",
    thumbnail: "",
    description:
      "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
  },
  {
    id: 10,
    name: "Magic tree",
    thumbnail: "",
    description:
      "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
  },
  {
    id: 11,
    name: "Blue Fire",
    thumbnail: "",
    description:
      "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
  },
  {
    id: 12,
    name: "Witch Party",
    thumbnail: "",
    description:
      "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
  },
]);
</script>

<style lang="css" scoped>
.games-container {
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.game-title {
  font-size: 60px;
  font-weight: 900;
  line-height: 60px;
  font-family: "Playfair Display";
  padding-bottom: 24px;
}

.game-description {
  font-family: "Montserrat";
  font-style: italic;
  color: #757575;
  font-weight: 400;
  width: 860px;
  text-align: center;
}
.game-item {
  overflow: hidden;
}
.isChan {
  padding-top: 40px;
}

@media (min-width: 1366px) {
  /* style list game */
  .list-game {
    display: grid;
    grid-template-columns: auto auto auto auto;
    column-gap: 40px;
    padding: 80px 80px 0px 80px;
  }
}

@media (min-width: 357px) and (max-width: 1365px) {
  .game-title {
    font-family: "Playfair Display";
    font-size: 40px;
    font-weight: 900;
    line-height: 50px;
    letter-spacing: 0.6000000238418579px;
    text-align: center;
    padding-bottom: 16px;
  }

  .game-description {
    width: 90%;
  }

  .list-game {
    display: grid;
    grid-template-columns: auto auto;
    column-gap: 15px;
    padding: 40px 16px 0;
  }
}
</style>
