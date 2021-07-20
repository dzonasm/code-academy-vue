<template>
	<div>
		{{ counter }}
	</div>
	<button @click="increment()">
		Click me
	</button>
</template>

<script>
export default {
	name: "Increment",
	props: {
		msg: String,
	},
	data() {
		return {
			counter: 0,
		};
	},
	methods: {
		increment() {
			this.counter = this.counter + 5;
		},
	},
};
</script>
