<template>
<div class="block" @click="stopTimer" v-if="showBlock">
  Click Here
</div>
</template>

<script>
export default {
  name: "Block",
  data(){
    return {
      showBlock: false,
      score:0,
      timer:null
    }
  },
  props:['delay'],
  mounted(){
    setTimeout(()=>{
      this.showBlock=true;
      this.startTimer();
    },this.delay)
  },
  methods:{
    startTimer(){
      this.timer=setInterval(()=>{
        this.score+=50
      },50)
    },
    stopTimer(){
      clearInterval(this.timer);
      this.$emit("endGame",this.score);
    }
  }


}
</script>

<style scoped>
.block{
  width: 400px;
  height: 300px;
  background-color: skyblue;
  color: white;
  text-align: center;
  margin: 10px 0;
  padding-top: 20px;
}
</style>