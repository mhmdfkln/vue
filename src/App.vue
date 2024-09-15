<template>
  <div id="app">
    <div class="container">
      <h1>Vue Click Counter and Box Color Changer</h1>

      <!-- Click Counter -->
      <div class="counter-section">
        <button @click="decrementCounter">-</button>
        <button @click="incrementCounter">+</button>
        <button @click="resetCounter">Reset</button>
        <p>Current count: {{ counter }}</p>
      </div>

      <!-- Color Box -->
      <div class="color-section">
        <div :style="{ backgroundColor: boxColor }" class="color-box"></div>
        <button @click="changeColor('red')">Red</button>
        <button @click="changeColor('blue')">Blue</button>
        <button @click="changeColor('green')">Green</button>
        <button @click="changeColor('yellow')">Yellow</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      counter: 0,
      boxColor: 'gray', // Initial color
    };
  },
  methods: {
    incrementCounter() {
      this.counter += 1;
    },
    decrementCounter() {
      this.counter -= 1;
    },
    resetCounter() {
      this.counter = 0;
    },
    changeColor(color) {
      this.boxColor = color;
    }
  }
};
</script>

<style>
#app {
  text-align: center;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  color: #2c3e50;
  margin-top: 60px;
}

.container {
  max-width: 600px;
  margin: 0 auto;
}

.counter-section,
.color-section {
  margin-bottom: 20px;
}

button {
  margin: 5px;
  padding: 10px 20px;
  font-size: 16px;
  cursor: pointer;
}

.color-box {
  width: 200px;
  height: 200px;
  margin: 20px auto;
  border: 1px solid #ccc;
}
</style>
