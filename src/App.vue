<template>
  <div id="app">
    <Animation />
    <Piano />
  </div>
</template>

<script>
import Animation from './components/AlerteAnim.vue'
import InterfaceManager from './InterfaceManager.vue'
import Piano from './components/Piano.vue'

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
    console.log(datajs)
  document.querySelector('object, embed').openroom(datajs)
  },
  components: {
    Animation,
    Piano
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
      case 'piano':
        if(JSON.parse(a).data == 'open'){
          InterfaceManager.props.piano.show = true
        }  else {
          InterfaceManager.props.piano.show = false
        }
        break;
      case 'pianonote':
       if(JSON.parse(a).note) {
        var audio = new Audio("http://127.0.0.1/audio/" + JSON.parse(a).note + ".mp3");
        audio.play();
        break;
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
