<template>
<h1>hello, soufiane</h1>
<button @click="start" v-if="!isplaying">click me</button>
<block v-if="isplaying" :delay="delay" @end="endgame"/>

<res :scor="scor" v-if="showresult"/>
</template>

<script>

import block from './components/block.vue';
import res from './components/result.vue';


export default {
  name: 'App',
  components: {
    block,
    res
  },
  data(){
    return{
        isplaying:false,
        delay:null,
        scor:0,
        showresult:false
    }
  },
  methods: {
    start(){
        this.delay=200+Math.random()*5000.
        this.isplaying=true;
        this.showresult=false;
        // alert(this.delay);
    },
    endgame(reaction)
    {
      this.scor=reaction
      // alert(this.scor)
      this.isplaying=false
      this.showresult=true;
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
  margin-top: 60px;
}

button{
  background:#0faf87;
  color:white;
  border:none;
  padding:8px 16px;
  border-radius:4px;
  font-size:16px;
  letter-spacing: 1px;
  cursor:pointer;
  margin:10px;
}
</style>
