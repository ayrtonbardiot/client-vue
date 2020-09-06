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
  components: {
    Animation
  }
  
}

/** window.FlashExternalInterface.openHabblet = function(a, b){
    const data = JSON.parse(a);
    console.debug(b);
    console.log(this.getManager());
        this.getManager().animation.username = data.username
        this.getManager().animation.show = true 
}**/
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
