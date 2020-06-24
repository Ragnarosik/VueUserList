<template>
	<section class="user-detail">
		<div class="definition">{{'Информация о пользователе'}}</div>
		<user-detail v-if="user" :user="user"></user-detail>
	</section>
</template>



<script>
	import UserDetail from "../components/UserDetail.vue";

	export default {
		components: {
			UserDetail
		},
		props: {
			users: Array,
			username: String
		},
		data() {
			return {};
		},
		computed: {
			user() {
				return this.users.find(user => user.username === this.username);
			}
		},
		mounted() {
			let rootUpdated = this.$route.params.username;
			let rootFind = this.users.find(user => user.username === rootUpdated);

			if (rootFind === undefined) {
				this.$router.push({ name: "users" });
			}
		}
	};
</script>


<style lang="scss">

	.definition {
		text-align: center;
		color: #726452;
		font-family: "Times New Roman";
		font-size: 3em;
		font-weight: 300;
	}
</style>