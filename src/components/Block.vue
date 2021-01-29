<template>
  <div class="block" v-if="showBlock" @click="blockClick">click here {{delay}}</div>
</template>

<script>
// import { onMounted } from 'vue'
export default {
    props:['delay'],
    data(){
      return{
        showBlock:false,
        score:0,
        timer:null
      }
    },
   mounted(){
    setTimeout(() => {
      this.showBlock=true;
      this.startTimer();
    }, this.delay);
   },
   methods:{
     startTimer(){
       this.timer=setInterval(() => {
         this.score+=50;
       }, 50);
     },
     blockClick(){
       clearInterval(this.timer);
       this.$emit("endGame",this.score);
     }
   }
  
  
}
</script>

<style>
.block{
    background-color: aquamarine;
    width:500px;
    height: 400px;
    text-align: center;
    margin-top: 20px;
    margin-left:450px;
    padding-top:30px;
}

</style>