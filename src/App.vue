<template>
  <h1>Reaction Timer..Be your own Champ</h1>
  <button @click='start' :disabled='isPlaying'>play</button>
  <Block v-if='isPlaying' v-bind:delay='delay' @end='endGame'/>
  <Results v-if='showResults' :result='score'/>
</template>

<script>
import Block from './components/Block.vue'
import Results from './components/Results.vue'

  export default{
    name : 'App',
    components : {
      Block,Results,
    },
    data(){
      return{
        isPlaying : false,                               //true if playing..false if not playing (at start too)
        delay: null,
        score:null,
        showResults : false,
      }
    },
    methods:{
      start(){
        this.delay = 2000 + Math.random() * 5000,       //bw 2s-7s any random time
        this.isPlaying = true
        this.showResults = false
      },
      endGame(reactTime){
        this.score = reactTime
        this.showResults = true
        this.isPlaying = false
      },
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
button{
  background: #0faf87;
  color : white;
  border : none;
  padding: 8px 16px;
  border-radius: 4px;
  font-size: 16px;
  letter-spacing: 1px;
  cursor: pointer;
  margin : 10px;
}
button[disabled]{
  capacity : 0.3;
  cursor : not-allowed;
}

</style>
