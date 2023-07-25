<template>
  <h1>Reaction time</h1>
  <button @click="startGame" :disabled="isPlaying">Play</button>
  <Block v-if="isPlaying" :delay="delay" @end="stopGame"/>
  <Results v-if="showResult" :result="result"/>
</template>

<script>
import Block from './components/Block.vue'
import Results from "./components/Results.vue"
export default {
  components:{Block,Results},
  data(){
    return {
      isPlaying: false,
      delay: null,
      showResult: false,
      result: null,
    }
  },
  methods:{
    startGame(){
      this.showResult=false;
      this.isPlaying=true;
      this.delay = 1000+ Math.random()*3000;
    },
    stopGame(result){
      this.result = result;
      this.showResult = true;
      this.isPlaying = false;
      
    }
  }
}
</script>

<style>

</style>