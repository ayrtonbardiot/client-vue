<template>
  <transition name="fade" mode="out-in">
    <div id="animation_box" class="cookieConsentContainer" v-show="data.animation.show">
    <div class="cookieTitle" style="margin-right: 66%"><a>Nouvelle animation !</a></div>
    <div class="box_cross" v-on:click="data.animation.show = !data.animation.show"></div>
    <div class="avatarImage">
    <img id="lookuser" v-bind:src="'https://avatar-api.com/habbo-imaging/avatarimage?figure=' + data.animation.look + '&gesture=sml&action=wav&head_direction=3'">
    </div>
      <div class="cookieDesc">
        <p>Une nouvelle animation a démarré chez {{ data.animation.username }} ! {{ data.animation.msg }} </p>
      </div>
    <div class="cookieButton"><a id="rejoindre_btn">Rejoindre !</a></div>
  </div>
  </transition>
</template>

<script>
import App from '../App.vue';
    export default {
        name: 'AlerteAnim',
        data() {
            return {
              data: App.getManager()
            }
        },
    }
</script>

<style>
.fade-enter-active, .fade-leave-active {
  transition: opacity .5s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
.box_cross {
        background-image: url('~@/img/close.png');
        position: absolute;
    margin-top: 23px;
    margin-right: 10px;
        top: 7px;
        right: 7px;
        width: 19px;
        height: 20px;
        cursor: pointer;
    }
.box_cross:hover {
          background-image: url('~@/img/close_hover.png');
        position: absolute;
    margin-top: 23px;
    margin-right: 10px;
        top: 7px;
        right: 7px;
        width: 19px;
        height: 20px;
        cursor: pointer;
}   
.box_cross:active {
          background-image: url('~@/img/close_active.png');
        position: absolute;
    margin-top: 23px;
    margin-right: 10px;
        top: 7px;
        right: 7px;
        width: 19px;
        height: 20px;
        cursor: pointer;
}   
.cookieConsentContainer {
  z-index: 999;
  width: 652px;
  min-height: 20px;
  box-sizing: border-box;
  padding: 30px 30px 30px 30px;
  background: #232323;
  overflow: hidden;
  position: fixed;
    bottom: 30px;
  right: 30px;
  display: block;
}
.cookieConsentContainer .cookieTitle a {
  font-family: OpenSans, arial, "sans-serif";
  color: #FFFFFF;
  font-size: 22px;
  line-height: 20px;
  display: block;
}
.cookieConsentContainer .cookieDesc p {
  margin: 0;
  padding: 0;
  font-family: OpenSans, arial, "sans-serif";
  color: #FFFFFF;
  font-size: 13px;
  line-height: 20px;
  display: block;
  margin-top: 10px;
  float: left;
} .cookieConsentContainer .cookieDesc a {
  font-family: OpenSans, arial, "sans-serif";
  color: #FFFFFF;
  text-decoration: underline;
}
.cookieConsentContainer .cookieButton a {
  display: inline-block;
  font-family: OpenSans, arial, "sans-serif";
  color: #FFFFFF;
  font-size: 14px;
  font-weight: bold;
  margin-top: 65px;
  background: #000000;
  box-sizing: border-box; 
  padding: 15px 24px;
  text-align: center;
}
.cookieConsentContainer .cookieButton a:hover { 
  cursor: pointer;
  background: #3E9B67;
}
.avatarImage {
  float: left;
}
.closeBtn {
  float: right;
}
@media (max-width: 980px) {
  .cookieConsentContainer {
    bottom: 0px !important;
    left: 0px !important;
    width: 100%  !important;
  }
}
</style>