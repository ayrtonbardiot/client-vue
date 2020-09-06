<template>
  <div id="app">
    <Animation></Animation>
  </div>
</template>

<script>
import Animation from './components/AlerteAnim.vue'
import InterfaceManager from './InterfaceManager.vue'
        
export default {
  name: 'App',
  data() {
    return {
      anim_show: "false",
      okok: "test"
    }
  },
  getManager: function() {
    return InterfaceManager.props;
  },
  components: {
    Animation
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
