<template>
	<div>
		{{ counter }}
	</div>
	<button @click="incrementOne()">
		Click me
	</button>
</template>

<script>
export default {
	name: "IncrementFive",
	props: {
		msg: String,
	},
	data() {
		return {
			counter: 0,
		};
	},
	methods: {
		incrementOne() {
			this.counter++;
		},
	},
};
</script>
