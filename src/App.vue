<template>
	<div id="app">
		<h1>This is VUE</h1>
		<img alt="Vue logo" src="./assets/logo.png" />

		<p>Välkommen {{ user.lastName }}, {{ user.firstName }}</p>
		<UserForm :user="user" @save="onSubmitForm" />
		<p>Välkommen {{ user2.lastName }}, {{ user2.firstName }}</p>
		<UserForm :user="user2" @save="onSubmitForm" />

		<div>
			Du ahr clickat {{ count }} gånger!
			<button @click="onBtnCLick">Klicka</button>
			<div v-if="count > 5">
				Bra klickat!!
			</div>
		</div>
	</div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue';
import UserForm from './components/UserForm.vue';

export default {
	name: 'App',
	components: {
		UserForm,
	},
	data() {
		return {
			user: {
				firstName: 'Janne',
				lastName: 'Kemi',
			},
			user2: {
				firstName: 'Jenni',
				lastName: 'Pulli',
			},
			count: 0,
		};
	},
	methods: {
		onBtnCLick() {
			console.log('Klick på knappen');
			this.count += 1;
		},
		onSubmitForm(evt) {
			console.log('Form submiteed');
			console.log(evt);
			console.log(evt.target);
		},
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
