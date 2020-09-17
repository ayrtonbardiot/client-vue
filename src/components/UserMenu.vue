<template>
        <div id="mySidenav" class="sidenav">
<a href="" class="closebtn" onclick="closeNav()">&times;</a>
  <p style="color: white;text-align: center;font-size: xx-large;margin: 0;">pseudo</p>
  <div class="okok7">
        <img src="https://cdn.discordapp.com/emojis/691366380053725236.png" style="width: 25px;height: 25px;margin-top: 40px;margin-right: 135px;">
        <p style="color: white;margin-top: -27px;margin-left: 30px;">1337 crédits</p>
        <img src="https://cdn.discordapp.com/emojis/743885976182587402.png" style="width: 25px;height: 25px;">
    <p style="color: white;margin-top: -27px;margin-left: 30px;">1337 duckets</p>
    <img src="http://localhost/ajax/gotwtest.png" style="width: 25px;height: 25px;">
    <p style="color: white;margin-top: -27px;margin-left: 30px;">1337 coquillages</p>
    </div>
  <hr style="
            margin-top: 14%;
            height: 185px;
            position:absolute;
            left: 50%;
            margin-left: -8.2%;
        ">
        
  <img id="testuser8" src="https://www.avatar-api.com/habbo-imaging/avatarimage?figure=&amp;size=l&amp;direction=3&amp;head_direction=3&amp;gesture=sml&action=wav" style="filter: drop-shadow(2px 2px 0 white)   drop-shadow(-2px 2px 0 white)  drop-shadow(2px -2px 0 white)         drop-shadow(-2px -2px 0 white);">
  <hr style="width: 55%; margin-top: 9%;">
        </div>
</template>

<script>
import App from '../App.vue';
    export default {
        name: 'UserMenu',
        data() {
            return {
              data: App.getManager()
            }
        },
    }
</script>

<style scoped>
body {
  font-family: "Lato", sans-serif;
}

.sidenav {
  height: 100%;
  width: 0;
  position: fixed;
  z-index: 1;
  top: 0;
  left: 0;
  background-color: #111;
  overflow-x: hidden;
  transition: 0.5s;
  padding-top: 60px;
}

.sidenav a {
  padding: 8px 8px 8px 32px;
  text-decoration: none;
  font-size: 25px;
  color: #818181;
  display: block;
  transition: 0.3s;
}

.sidenav a:hover {
  color: #f1f1f1;
}

.sidenav .closebtn {
  position: absolute;
  top: 0;
  right: 25px;
  font-size: 36px;
  margin-left: 50px;
}



@media screen and (max-height: 450px) {
  .sidenav {padding-top: 15px;}
  .sidenav a {font-size: 18px;}
}

.okok7{
  float: right;
}
</style>