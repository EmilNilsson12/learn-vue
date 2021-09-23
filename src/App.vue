<template>
	<div id="app">
		<h1>This is VUE</h1>
		<img alt="Vue logo" src="./assets/logo.png" />
		<!-- <HelloWorld msg="Welcome to Your Vue.js App" /> -->

		<p>Välkommen {{ user.lastName }}, {{ user.firstName }}</p>
		<p>Välkommen {{ user2.lastName }}, {{ user2.firstName }}</p>

		<div>
			Du ahr clickat {{ count }} gånger!
			<button @click="onBtnCLick" onClick>Klicka</button>
			<div v-if="count > 5">
				Bra klickat!!
			</div>

			<div>
				<form action="" @submit="onSubmitForm">
					<p>
						Hello.
					</p>
					<p>
						My <label for="firstName">first name</label> is
						<input
							id="firstName"
							v-model="user.firstName"
							type="text"
							required
						/>.
					</p>
					<p>
						My <label for="lastName">last name</label> is
						<input id="lastName" v-model="user.lastName" type="text" />.
					</p>
					<button type="submit">Skicka in svaret</button>
				</form>
			</div>
		</div>
	</div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue';

export default {
	name: 'App',

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
			evt.preventDefault();
			console.log('Form submiteed');
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
