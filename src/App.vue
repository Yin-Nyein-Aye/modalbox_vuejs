<template>  
  <h1>How can you catch me fast?</h1>
  <button @click="start" :disabled="isPlaying">Play</button>
  <div v-if="isPlaying">
    <Block :delay="delay" @endGame="endGame" />
  </div> 
  <div v-if="end">
    <Result :score="score" />
  </div>
</template>

<script>
import Block from "./components/Block.vue"
import Result from "./components/Result.vue"
export default {
  name: 'App',
  components: {
    Block,Result
  },
  data(){
    return{
        isPlaying:false,
        delay:null,
        score:0,
        end:false
    }
  },
  methods:{
      start(){
        this.isPlaying=true;
        this.delay=2000+Math.random()*5000;
        this.end=false;
      },
      endGame(score){
        this.score=score;
        this.isPlaying=false;
        this.end=true;
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
body{
background:linear-gradient(rgb(163, 229, 163),rgb(173, 127, 173));
background-attachment: fixed;
}
button{
  font-size:15px;
  padding: 10px 15px;  
  border-radius: 30px;
}
</style>
