<template>
  <div class="modal">
    <h2 v-if="uiState === 'won'">You Win !</h2>
    <h2 v-else-if="uiState === 'lost'">You lost !</h2>
    <svg
      xmlns="http://www.w3.org/2000/svg"
      viewBox="0 0 131 131"
      aria-labelledby="face"
      role="presentation"
      width="70"
      height="70"
    >
      <title id="face">Face Icon</title>
      <circle class="cls-1" cx="65.5" cy="65.5" r="64" />
      <circle class="cls-2" cx="95" cy="65.8" r="7.5" />
      <circle class="cls-2" cx="36" cy="65.8" r="7.5" />
      <path
        class="cls3"
        d="M51,97s6,10,23,10S95,97,95,97"
        transform="translate(-8.5 -5.5)"
      />
    </svg>
    <button @click="restartGame">Let's play again</button>
  </div>
</template>

<script>
import { mapState } from "vuex";
export default {
  computed: {
    ...mapState(["uiState"]),
  },
  methods: {
    restartGame() {
      this.$store.commit("restartGame");
    },
  },
};
</script>

<style lang="scss" scoped>
.cls-1 {
  fill: #fbb040;
  stroke: #231f20;
}

.cls-1,
.cls-3 {
  stroke-miterlimit: 10;
  stroke-width: 3px;
}

.cls-2 {
  fill: #231f20;
}

.cls-3 {
  fill: none;
  stroke: #be1e2d;
}
</style>
