<template>
	<div>
		<img alt="Vue logo" src="./assets/logo.png" />

		<Quiz></Quiz>
	</div>
</template>

<script>
import Quiz from "./components/Quiz.vue";

export default {
	name: "App",
	components: {
		Quiz,
	},
	data() {
		return {
			arr: ["hello", "world", "im vue"],
			string: "heyo im a string yall",
			last: false,
		};
	},
};
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
