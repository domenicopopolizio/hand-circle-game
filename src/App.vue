<template>
  <div id="app"> 
    <camera></camera>
    <hand-trigger @click="handOut = !handOut"></hand-trigger>
    <hand :isOut="handOut"></hand>
  </div>
</template>

<script> 
import HandTrigger from './components/HandTrigger';
import Camera from './components/Camera';
import Hand from './components/Hand';

export default {
  name: 'app',
  components: { 
    HandTrigger, Camera, Hand
  },
  data() {
    return { 
      handOut: false
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale; 
  color: #2c3e50;
  margin-top: 60px;
}

</style>
