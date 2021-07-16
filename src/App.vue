<template>
  <h1>Reaction test</h1>
  <button @click="start" :disabled="isPlaying">Play</button>
  <block v-if="isPlaying" :delay="delay" @end="endGame" />
  <results v-if="showResults" :score="score" />
  </template>

<script>
import block from './components/Block.vue'
import results from './components/Results.vue'

export default {
  name: 'App',
  components: { block, results },
  data () {
    return {
      isPlaying: false,
      delay: null,
      score:null,
      showResults: false
    }
  },
  methods:{
    start() {
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true
      this.showResults = false
      //console.log(this.delay)
    },
    endGame(reactionTime) {
      this.score = reactionTime
      this.isPlaying = false
      this.showResults = true
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
  color: #444;
  margin-top: 60px;
}
button {
  background: #0fa;
  color:white;
  border:none;
  padding: 8px 16px;
  border-radius: 4px;
  font-size: 16px;
  letter-spacing: 1px;
  cursor: pointer;
  margin: 10px;
}
button[disabled] {
  opacity: 0.2;
  cursor: not-allowed;
}
</style>
