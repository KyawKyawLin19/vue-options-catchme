<template>
  <div>
    <h1>How fast can u catch me?</h1>
    <button @click="start" :disabled="isPlaying">Play</button>
    <Block v-if="isPlaying" :delay="delay" @endGame="end"></Block>
    <Score v-if="showResult" :result = result></Score>
  </div>
</template>

<script>
import Block from "./components/Block.vue"
import Score from "./components/Score.vue"
export default {
  name: 'App',
  components: {
    Block, Score
  },
  data() {
    return {
      isPlaying : false,
      delay : null,
      result: 0,
      showResult : false,
    }
  },
  methods: {
    start() {
      this.isPlaying = true;
      this.delay = 2000+Math.random()*5000;
    },
    end(score) {
      this.result = score;
      this.isPlaying = false;
      this.showResult = true;
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
