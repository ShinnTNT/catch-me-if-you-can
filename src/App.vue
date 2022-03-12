<template>
  <div>

  <h1>how fast can you catch me</h1>
  <button @click="start" :disabled="isPlaying">Play</button>
    <div v-if="isPlaying">
      <Block :delay="delay" @endGame="endGame"></Block>
    </div>

  <div v-if="end">
    <Result :score="score"></Result>
  </div>
  </div>
</template>

<script>
import Block from "@/components/Block";
import Result from "@/components/Result";
export default {
  name:"App",
  components: {Result, Block},
  data(){
    return {
      isPlaying:false,
      delay:null,
      score:0,
      end:false
    }
  },
  methods:{
    start(){
      this.delay=2000+Math.random()*5000;
      this.isPlaying = true;
    },
    endGame(score){
       this.score=score;
       this.isPlaying = false;
       this.end=true
    }
  }
}
</script>

<style scoped>

</style>