<template>
  <div id="app">
    <GameScreen v-if="gameStarted" />
    <Home v-else v-on:start-game="startGame" />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";

import Home from "./views/Home.vue";
import GameScreen from "./views/GameScreen.vue";

@Component({
  components: {
    Home,
    GameScreen
  }
})
export default class App extends Vue {
  gameStarted: boolean = false;

  startGame() {
    this.gameStarted = true;
  }
}
</script>

<style>
html {
  height: 100vh;
}

body {
  margin: 0;
  padding: 0;
  width: 100%;
  min-height: 100vh;
}

* {
  box-sizing: border-box;
}

#app {
  height: 100vh;
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
