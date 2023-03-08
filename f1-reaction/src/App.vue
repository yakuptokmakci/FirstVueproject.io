<template class="f1">
  <h1>Welcome to the start timer test </h1>
  <p>basicliy this test's purpose is made to put your reaction time to the test </p>
  <p>after pressing the play button you just need to press green box then you can see your reaction time score </p>
  <button @click="startgame" :disabled="isplaying">Play</button>
  <Block v-if="isplaying" :delay="delay" @end="endgame">
  </Block>
  <Results v-if="showresults" :score="score"></Results>


</template>

<script>
import Block from './components/Block.vue'
import Results from './components/Results.vue';

export default {
  name: 'App',
  components: {Block, Results},
  data(){
    return{
      delay:null,
      isplaying:false,
      score:null,
      showresults:false
    }
  },
  methods:{
    startgame(){
      this.isplaying=true;
      this.delay=2000+ Math.random()*5000
      console.log(this.delay)
      this.showresults=false
    },
    endgame(reactiontime){
      this.score=reactiontime
      this.isplaying=false
      this.showresults=true
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background: rgba(88, 80, 80, 0.5);
  margin-top: 60px;
}
h1 {
  font-size: 70px;
  font-weight: 600;
  background-image: linear-gradient(to left, #FF0000, #FF0000);
  color: transparent;
  background-clip: text;
  -webkit-background-clip: text;
}
p{
  font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
  
}
button{
  background-color: rgb(9, 197, 197);
  color: white;
  border: none;
  padding: 8px 16px;
  border-radius: 4px;
  font-size: 16px;
  letter-spacing: 1px;
  cursor: pointer;
  margin: 10px;
}
button[disabled]{
  opacity: 0.2;
  cursor: not-allowed;
}


</style>
