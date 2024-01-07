<template>
	<div>
		<h2 v-html="html"></h2>
	</div>
</template>

<script>
import { ref } from 'vue';

export default {
	setup() {
		const html = ref('<strong>스트롱</strong>');

		return {
			html,
		};
	},
};
</script>

<style lang="scss" scoped></style>
