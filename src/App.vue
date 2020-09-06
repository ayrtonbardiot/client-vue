<template>
  <div id="app">
    <Animation />
  </div>
</template>

<script>
import Animation from './components/AlerteAnim.vue'
import InterfaceManager from './InterfaceManager.vue'
export default {
  name: 'App',
  data() {
    return {
    }
  },
  getManager: function() {
    return InterfaceManager.props;
  },
  sendData: function(datajs) {
  document.querySelector('object, embed').openroom(datajs)
  },
  components: {
    Animation
  }
  
  
}

window.FlashExternalInterface.openHabblet = function(a, b){
  console.log(a, b);
  switch(JSON.parse(a).header){
    case 'animation':
        InterfaceManager.props.animation.username = JSON.parse(a).username
        InterfaceManager.props.animation.look = JSON.parse(a).look
        InterfaceManager.props.animation.msg = JSON.parse(a).message
        InterfaceManager.props.animation.idroom = JSON.parse(a).idroom
        InterfaceManager.props.animation.show = true
        break;
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
