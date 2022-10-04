<template>
	<div>{{ reactiveMessage }}</div>
	<button v-on:click="addReactiveMessage">Add Meassage</button>
	<div>{{ normalMessage }}</div>
	<button v-on:click="addNomalMessage">Add Meassage</button>
</template>

<script>
import { ref, onMounted, onBeforeMount } from 'vue';
export default {
	setup() {
		console.log('setup()');
		const reactiveMessage = ref('hello word');
		const addReactiveMessage = () => {
			reactiveMessage.value += '!';
		};

		//console.log(isRef(reactiveMessage)); // true

		let normalMessage = 'hello normal word';

		const addNomalMessage = () => {
			normalMessage += '!';
		};

		onMounted(() => {
			console.log('onMounted');
		});

		onBeforeMount(() => {
			console.log('onBeforeMount');
		});
		return {
			reactiveMessage,
			normalMessage,
			addReactiveMessage,
			addNomalMessage,
		};
	},
};
</script>

<style lang="scss" scoped></style>
