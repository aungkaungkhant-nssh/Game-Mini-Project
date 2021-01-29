<template>
 <h1>How fast can you catch me?</h1>
  <button @click="showBlock" :disabled="isPlaying">Play</button>
  <div v-if="isPlaying">
      <Block :delay="delay" @endGame="endGame"/>
  </div>
  <div v-if="showResult">
        <Result :score="score"/>
  </div>

</template>

<script>

import Block from "./components/Block.vue";
import Result from "./components/Result.vue";
export default {
  name: 'App',
  components: {
   Block,
   Result
  },
  data(){
    return{
      isPlaying:false,
      delay:null,
      score:0,
      showResult:false
    }
  },
  methods:{
    showBlock(){
      this.isPlaying=true;
      this.delay=2000+Math.random()*5000;

    },
    endGame(score){
       this.score=score;
       this.showResult=true;
       this.isPlaying=false
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
