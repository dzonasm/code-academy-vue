<template>
	<div>
		{{ inputVal }}
	</div>
	<button @click="increment()">
		Click me
	</button>

	<input v-model="inputVal" type="text" />
	<button @click="logInput()">
		Click me
	</button>
</template>

<script>
export default {
	name: "IncrementTen",
	props: {
		msg: String,
	},
	data() {
		return {
			counter: 0,
			inputVal: "",
		};
	},
	methods: {
		increment() {
			this.counter = this.counter + 10;
		},
	},
};
</script>
