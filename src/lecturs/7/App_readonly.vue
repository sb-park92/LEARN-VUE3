<template>
	<div>
		<p>text : {{ text }}</p>
		<button v-on:click="increText">증가</button>
		<p>ab : {{ ab }}</p>
		<button v-on:click="increAb">증가</button>
	</div>
</template>

<script>
import { readonly, ref } from 'vue';

export default {
	setup() {
		const text = ref(0);
		const increText = () => {
			text.value++;
		};
		const ab = readonly(text);
		const increAb = () => {
			ab.value++;
		};
		return { text, increText, ab, increAb };
	},
};
</script>

<style lang="scss" scoped></style>
