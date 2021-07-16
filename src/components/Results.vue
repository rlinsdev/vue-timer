<template>
  <p>Reaction time: {{score}} ms</p>
  <p class="rank">{{rank}}</p>
</template>

<script>
export default {
  props: ['score'],
  data() {
    return {
      rank:null
    }
  },
  mounted(){
    if(this.score < 250){
      this.rank = 'ninja fingers!'
    } else if (this.score <4000){
      this.rank = 'Rapid relexes'
    } else {
      this.rank = 'Snail peace'
    }
  }

}
</script>

<style>
.rank{
  font-size: 1.4em;
  color:#0fa;
  font-weight:bold;
}
</style>