<template>
	<div>
		<p>author</p>
		<h2>{{ author }}</h2>
		<p>title</p>
		<h2>{{ title }}</h2>
	</div>
</template>

<script>
import { reactive, toRef } from 'vue';

export default {
	setup() {
		const book = reactive({
			author: 'Vue Team',
			year: '2020',
			title: 'Vue 3 Guide',
			description: '당신은 이 책을 지금 바로 읽습니다 ;)',
			price: '무료',
		});
		// const { author, title } = toRefs(book);
		const author = toRef(book, 'author');
		const title = toRef(book, 'title');
		return { author, title };
	},
};
</script>

<style lang="scss" scoped></style>
