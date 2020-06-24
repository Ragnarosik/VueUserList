<template>
	<div class="users">
		<div class="definition">{{'Список пользователей'}}</div>
		<input type="text" placeholder="Поиск..." style="margin-left: 690px; width: 520px; height: 30px; font-size: medium;" v-model="usersName" autofocus>
		<users-list :users="users" :isHidden="isHidden" :isSmall="isSmall" @remove="userRemove"></users-list>
		<users-buttons @random="setRandom" @show="setShow"></users-buttons>
	</div>
</template>


<script>
	import UsersList from "../components/UsersList.vue";
	import UsersButtons from "../components/UsersButtons.vue";

	export default {
		components: {
			UsersList,
			UsersButtons
		},
		props: {
			users: []
		},
		data() {
			return {
				isHidden: false,
				isSmall: false,
				usersName: []
			};
		},
		methods: {
			setShow() {
				this.isHidden = !this.isHidden;
				this.isSmall = !this.isSmall;
			},
			setRandom() {
				this.users.sort(() => Math.random() - 0.5);
			},
			userRemove(userToRemove) {
				this.users.splice(this.users.indexOf(userToRemove), 1);
			}
		},
	};
</script>




<style lang="scss" scoped>
	.users {
		padding-bottom: 6rem;
	}

	.definition {
		text-align: center;
		color: #726452;
		font-family: "Times New Roman";
		font-size: 3em;
		font-weight: 300;
	}
</style>
