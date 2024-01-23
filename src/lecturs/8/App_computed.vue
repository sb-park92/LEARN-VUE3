<template>
	<div>
		<h2>{{ teacher.name }}</h2>
		<h3>강의가 있습니까?</h3>
		<p>{{ hasLecture }}</p>
		<p>{{ hasLecture }}</p>

		<p>{{ hasLecture }}</p>
		<p>{{ existLecture() }}</p>
		<p>{{ existLecture() }}</p>
		<p>{{ existLecture() }}</p>

		<h2>이름2</h2>
		<p>{{ fullName }}</p>
	</div>
</template>

<script>
import { computed, reactive, ref } from 'vue';

export default {
	setup() {
		let teacher = reactive({
			name: 'PSB',
			lectures: ['HTML/CSS', 'JAVASCRIPT', 'VUE3'],
		});
		const hasLecture = computed(() => {
			console.log('computed');
			return teacher.lectures.length > 0 ? '있음 ＠' : '없음 ★';
		});
		const existLecture = () => {
			console.log('methoed');
			return teacher.lectures.length > 0 ? '있음 ＠' : '없음 ★';
		};
		const firstName = ref('홍');
		const lastName = ref('길동');

		// const fullName = computed(() => firstName.value + ' ' + lastName.value);
		// console.log('fuleName : ', fullName.value);
		const fullName = computed({
			get() {
				return firstName.value + ' ' + lastName.value;
			},
			set(value) {
				[firstName.value, lastName.value] = value.split(' ');
			},
		});

		fullName.value = '박 성빈';
		return { teacher, hasLecture, existLecture, fullName };
	},
};
</script>

<style lang="scss" scoped></style>
