<template>
	<div id="app" v-cloak>
		<page-header></page-header>

		<main class="page-main">
			<page-title></page-title>

			<router-view :users="users" />
		</main>
	</div>
</template>



<script>
	import PageHeader from './components/PageHeader.vue'
	import PageTitle from './components/PageTitle.vue'

	export default {
		components: {
			PageHeader,
			PageTitle,
		},
		data() {
			return {
				users: []
			}
		},
		created() {
			fetch('https://randomuser.me/api/?results=10')
				.then(res => res.json())
				.then(data => {
					this.users = data.results.map(user => ({
						name: user.name,
						username: user.login.username,
						birthdate: user.dob.date,
						age: user.dob.age,
						gender: user.gender,
						nationality: user.nat,
						streetNumber: user.location.street.number,
						streetName: user.location.street.name,
						city: user.location.city,
						state: user.location.state,
						postcode: user.location.postcode,
						latitude: user.location.coordinates.latitude,
						longitude: user.location.coordinates.longitude,
						registered: user.registered.date,
						phone: user.phone,
						cell: user.cell,
						email: user.email,
						imageMedium: user.picture.medium,
						imageLarge: user.picture.large,
					}))
				})
		},
	};
</script>



<style lang="scss">
	@import url("https://fonts.googleapis.com/css?family=Oxygen:400,700,300");
	@import url("https://use.fontawesome.com/releases/v5.8.2/css/all.css");



	[v-cloak] {
		display: none;
	}

	*,
	*:after,
	*:before {
		margin: 0;
		padding: 0;
		box-sizing: border-box;
	}

	body {
		padding: 4.5rem 0 0;
		-webkit-font-smoothing: antialiased;
		font-family: "Oxygen", Helvetica, sans-serif;
		font-size: 62.5%;
		color: #726452;
		background-color: #e3e3e3;
	}

	a {
		text-decoration: none;
	}

	button {
		appearance: none;
		outline: none;
	}

	.page-main {
		padding: 4rem 0 0;
	}
	.v-enter {
		opacity: 0;
	}

	.v-enter-active {
		transition: opacity 1s;
	}

	.v-leave-to {
		opacity: 0;
	}

	.v-leave-active {
		transition: opacity 0.5s linear 0.5s;
	}
</style>
