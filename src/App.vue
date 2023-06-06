<script setup>
import { ref, reactive } from 'vue';
// const color = ref({
//   red: 0,
//   blue: 0,
//   green: 0,
// });

const color = reactive({
  red: 0,
  blue: 0,
  green: 0,
});

const selectRandomColor = () => {
  color.red = Math.floor(Math.random() * 255);
  color.blue = Math.floor(Math.random() * 255);
  color.green = Math.floor(Math.random() * 255);
};
</script>

<template>
  <main
    :style="{
      backgroundColor: `rgb(${color.red}, ${color.green}, ${color.blue})`,
    }"
  >
    <div>
      <input type="number" v-model="color.red" placeholder="red" />
      <input type="number" v-model="color.blue" placeholder="blue" />
      <input type="number" v-model="color.green" placeholder="green" />
      <button @click="selectRandomColor">Select random color</button>
    </div>
  </main>
  <Parent />
</template>

<style scoped>
main {
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}
div {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
</style>
