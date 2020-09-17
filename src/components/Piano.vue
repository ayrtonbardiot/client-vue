<template>
	<div v-show="data.piano.show" class="box" style="width: 340px;left: 200px;top: 200px;">
		<div class="box_head">
			<div class="box_cross" v-on:click="data.piano.show = !data.piano.show"></div>
			Piano
		</div>
		<div class="box_body">
			<div class="piano" v-show="data.piano.show" style="margin-right: -5%; margin-left: 2%;">
				<button class="white-key C4-key" v-on:click="playtest('c4')"></button>
				<button class="black-key Db4-key" v-on:click="playtest('db4')"></button>
				<button class="white-key D4-key" v-on:click="playtest('d4')"></button>
				<button class="black-key Eb4-key" v-on:click="playtest('eb4')"></button>
				<button class="white-key E4-key" v-on:click="playtest('e4')"></button>
				<button class="white-key F4-key" v-on:click="playtest('f4')"></button>
				<button class="black-key Gb4-key" v-on:click="playtest('gb4')"></button>
				<button class="white-key G4-key" v-on:click="playtest('g4')"></button>
				<button class="black-key Ab4-key" v-on:click="playtest('ab4')"></button>
				<button class="white-key A4-key" v-on:click="playtest('a4')"></button>
				<button class="black-key Bb4-key" v-on:click="playtest('bb4')"></button>
				<button class="white-key B4-key" v-on:click="playtest('b4')"></button>
				<button class="white-key C5-key" v-on:click="playtest('c5')"></button>
				<button class="black-key Db5-key" v-on:click="playtest('db5')"></button>
				<button class="white-key D5-key" v-on:click="playtest('d5')"></button>
				<button class="black-key Eb5-key" v-on:click="playtest('eb5')"></button>
				<button class="white-key E5-key" v-on:click="playtest('e5')"></button>
			</div>
		</div>
	</div>
</template>

<script>
import App from "../App.vue";
export default {
	name: "Piano",
	data() {
		return {
			data: App.getManager()
		};
	},
	methods: {
		playtest(sound) {
			if (sound) {
				App.sendData(JSON.stringify({ header: "pianonote", note: sound }));
			}
		}
	}
};
</script>

<style scoped>
.box {
	display: block;
	position: absolute;
	width: auto;
	height: auto;
	cursor: default;
	border: solid 1px #000;
	border-bottom: solid 3px;
	box-shadow: 2px 2px 0px rgba(0, 0, 0, 0.3);
	border-radius: 8px;
}
.box .box_head {
	display: block;
	background-color: #367897;
	border: solid 2px #408caf;
	border-bottom: solid 1px #000;
	border-top-left-radius: 7px;
	border-top-right-radius: 7px;
	font-size: 1.2em;
	line-height: 30px;
	text-align: center;
	color: #fff;
	font-weight: bold;
}
.box .box_body {
	display: block;
	height: 100%;
	background-color: #eceae0;
	border: solid 2px #fff;
	border-bottom-right-radius: 5px;
	border-bottom-left-radius: 5px;
	overflow: hidden;
}
.box .box_cross {
	background-image: url("~@/img/close.png");
	position: absolute;
      margin-top: 0px;
    margin-right: 0px;
	top: 7px;
	right: 7px;
	width: 19px;
	height: 20px;
	cursor: pointer;
}
.box .box_cross:hover {
	background-image: url("~@/img/close_hover.png");
}
.box .box_cross:active {
	background-image: url("~@/img/close_active.png");
}
.box .box_form {
	padding: 10px 17px;
	line-height: 22px;
}
.box .box_field {
	display: block;
}
.box label {
	display: block;
	font-weight: 900;
	margin-left: 2px;
}
.box select {
	box-sizing: border-box;
	width: 100%;
	height: 22px;
	color: #0d0d0d;
	border: 1px solid #000;
	border-radius: 3px;
	background-color: #fbfbf9;
	line-height: 17px;
	resize: none;
	overflow: hidden;
}
.box select:focus {
	outline: none;
}
.box .box_input_number {
	display: block;
	box-sizing: border-box;
	float: left;
	margin-right: 5px;
	width: 23px;
	height: 21px;
	color: #0d0d0d;
	border: 1px solid #959595;
	background-color: #fbfbf9;
	line-height: 17px;
}
.box .box_input_number:focus {
	outline: none;
}
.box .box_checkbox {
	padding: 10px;
}
.box .box_textarea {
	box-sizing: border-box;
	width: 100%;
	height: 42px;
	color: #0d0d0d;
	border: 1px solid #959595;
	background-color: #fbfbf9;
	line-height: 17px;
	resize: none;
	overflow: hidden;
}
.box .box_textarea:focus {
	outline: none;
}
.box .box_input {
	box-sizing: border-box;
	width: 100%;
	height: 21px;
	color: #0d0d0d;
	border: 1px solid #959595;
	background-color: #fbfbf9;
	line-height: 17px;
}
.box .box_input:focus {
	outline: none;
}
.box .box_button {
	display: block;
	width: 100%;
	padding: 7px;
	margin: 5px auto;
	background-image: -webkit-linear-gradient(#f3f3f3 50%, #d9d9d9 50%);
	box-shadow: 0 1px 0 #d9d9d9 inset, 1px 0 #d9d9d9 inset, -1px 0 #d9d9d9 inset,
		0 1px 0 #000;
	border-radius: 4px;
	border: 1px solid #000;
	font-weight: bold;
	color: #000;
	text-decoration: none;
	text-align: center;
	white-space: nowrap;
	cursor: pointer;
}
.box .box_button:hover {
	background-image: -webkit-linear-gradient(#f2f2f2 50%, #e1e1e1 50%);
	box-shadow: 0 1px 0 #e1e1e1 inset, 1px 0 #e1e1e1 inset, -1px 0 #e1e1e1 inset,
		0 1px 0 #000;
}
.box .box_button:active {
	background-image: -webkit-linear-gradient(#d2d2d2 50%, #989898 50%);
	box-shadow: 0 1px 0 #989898 inset, 1px 0 #989898 inset, -1px 0 #989898 inset,
		0 1px 0 #000;
}
.box .box_button:focus {
	outline: none;
}
.box .disabled {
	cursor: auto;
	background-image: -webkit-linear-gradient(#d4d4d4 50%, #b7b7b7 50%);
	box-shadow: 0 1px 0 #b7b7b7 inset, 1px 0 #b7b7b7 inset, -1px 0 #b7b7b7 inset,
		0 1px 0 #000;
}
.box .disabled:hover {
	background-image: -webkit-linear-gradient(#d4d4d4 50%, #b7b7b7 50%);
	box-shadow: 0 1px 0 #b7b7b7 inset, 1px 0 #b7b7b7 inset, -1px 0 #b7b7b7 inset,
		0 1px 0 #000;
}
.box .disabled:active {
	background-image: -webkit-linear-gradient(#d4d4d4 50%, #b7b7b7 50%);
	box-shadow: 0 1px 0 #b7b7b7 inset, 1px 0 #b7b7b7 inset, -1px 0 #b7b7b7 inset,
		0 1px 0 #000;
}
.box nav {
	position: relative;
	width: 100%;
	float: left;
}
.box nav .nav_sub {
	float: left;
	position: relative;
	background-color: #c3c2b8;
	font-size: 1.2em;
	padding: 10px;
	border-top-left-radius: 10px;
	border-top-right-radius: 10px;
	border: 1px solid #4d4c49;
	border-bottom: 1px solid #000;
	cursor: pointer;
}
.box nav .nav_sub:hover {
	border-bottom: 1px solid #eceae0;
	background-color: #f6f5f0;
	box-shadow: 1px 1px 2px #fff inset;
}
.box nav .bottom_lign {
	position: absolute;
	bottom: 0;
	left: 0;
	right: 0;
	border-bottom: 1px solid #000;
}
.box nav .active {
	border: 2px solid #000;
	border-bottom: 2px solid #eceae0;
	background-color: #eceae0;
	padding: 9px;
	box-shadow: 1px 1px 2px #fff inset;
}
.box nav .active:hover {
	border-bottom: 2px solid #eceae0;
	background-color: #eceae0;
}
.piano {
	display: flex;
	position: relative;
}

.white-key {
	width: 40px;
	height: 120px;
	background-color: #fff;
	border: 4px solid black;
	border-radius: 0 0 6px 6px;
	margin-left: -4px;
	outline: none;
	cursor: pointer;
}

.white-key:active {
	background-color: #c0c0c0;
}

.black-key {
	position: absolute;
	width: 24px;
	height: 80px;
	background-image: linear-gradient(#000000, #303030);
	border: 3px solid black;
	border-radius: 0 0 2px 2px;
	outline: none;
	cursor: pointer;
}

.black-key:active {
	background-image: linear-gradient(#000000, #101010);
}

.Db4-key {
	left: 22px;
}

.Eb4-key {
	left: 58px;
}

.Gb4-key {
	left: 130px;
}

.Ab4-key {
	left: 166px;
}

.Bb4-key {
	left: 202px;
}

.Db5-key {
	left: 274px;
}

.Eb5-key {
	left: 310px;
}
</style>
