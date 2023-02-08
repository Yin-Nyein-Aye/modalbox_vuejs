<template>
  <div class="block" v-if="showBlock" @click="stopTimer">Click Here</div>
</template>

<script>
export default {
    props:["delay"],
   data(){
    return{
        showBlock:false,
        timer:null,
        score:0
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
    stopTimer(){
        clearInterval(this.timer);
        this.$emit("endGame",this.score);
        
    }
   }
}
</script>

<style>
.block{    
    background-color: rgb(106, 109, 108);
    border-radius: 10px;

    width: 400px;    
    margin: 20px auto;
    color: whitesmoke;
    font-size: 20px;
    font-style: italic;
    padding: 150px 0;
    

}
</style>