<template>
  <h1>Reaction test</h1>
  <button @click="start" :disabled="isPlaying">Play</button>
  <block v-if="isPlaying" :delay="delay" />
</template>

<script>
import block from './components/Block.vue'

export default {
  name: 'App',
  components: { block },
  data () {
    return {
      isPlaying: false,
      delay: 1
    }
  },
  methods:{
    start() {
      this.delay = 2000
      this.isPlaying = true
      console.log(this.delay)
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
</style>
