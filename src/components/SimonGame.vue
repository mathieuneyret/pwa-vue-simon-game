<script setup lang="ts">
import { ref } from 'vue'

const colors = ["green", "red", "blue", "yellow"];
const arrayRandomColor = [];
const arrayClickColor = [];

function playSimon() {
  const randomColor = colors[Math.floor(Math.random()*colors.length)];
  console.log(randomColor);
}

function clickColor(color: any) {
  console.log(color);
}

</script>

<template>
  <h1>Simon Game</h1>

  <div class="simon-box">
    <div class="buttons">
      <button
          v-for="(color, index) in colors"
          :key="color"
          @click="clickColor(color)"
          :style="{ backgroundColor: color}"
          :value="color"
      >
      </button>
    </div>
    <br>
    <form @submit.prevent="playSimon">
      <button type="submit">submit</button>
    </form>
  </div>

</template>

<style scoped>
.simon-box {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.buttons {
  display: grid;
  grid-template-columns: repeat(2, 100px);
  gap: 10px;
}

.buttons button {
  height: 100px;
  opacity: 0.5;
}
</style>
