<template>
	<div>
		<form @submit.prevent="handleSubmit">
			<p>
				Hello.
			</p>
			<p>
				My <label for="firstName">first name</label> is
				<input id="firstName" v-model="user.firstName" type="text" required />.
			</p>
			<p>
				My <label for="lastName">last name</label> is
				<input id="lastName" v-model="user.lastName" type="text" />.
			</p>
			<button type="submit">Skicka in svaret</button>
		</form>
	</div>
</template>

<script>
export default {
	name: 'userform',
	props: {
		user: {
			type: Object,
		},
	},
	methods: {
		handleSubmit(evt) {
			this.$emit('save', evt);
		},
	},
	data() {
		return {
			name: 0,
		};
	},
};
</script>

<style scoped>
div {
	border: 1px solid black;
}
</style>
