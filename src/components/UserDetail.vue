<template>
	<div class="user-detail-data">
		<div class="user-detail-data__group user-detail-data__image">
			<img :src="user.imageLarge" alt />
		</div>

		<div class="user-detail-data__group user-detail-data__name">
			<p>
				<strong class="user-detail-data__label">Имя:</strong>
				{{user.name.title}} {{user.name.first}} {{user.name.last}}
			</p>
			<p>
				<strong class="user-detail-data__label">Никнейм:</strong>
				{{user.username}}
			</p>
			<p>
				<strong class="user-detail-data__label">Дата рождения:</strong>
				{{user.birthdate}}
			</p>
		</div>

		<div class="user-detail-data__group">
			<p>
				<strong class="user-detail-data__label">Возраст:</strong>
				{{user.age}}
			</p>
			<p>
				<strong class="user-detail-data__label">Пол:</strong>
				{{user.gender}}
			</p>
			<p>
				<strong class="user-detail-data__label">Национальность:</strong>
				{{user.nationality}}
			</p>
		</div>

		<div class="user-detail-data__group user-detail-data__location">
			<p>
				<strong class="user-detail-data__label">Страна:</strong>
				{{user.state}}
			</p>
			<p>
				<strong class="user-detail-data__label">Город:</strong>
				{{user.city}}
			</p>
			<p>
				<strong class="user-detail-data__label">Улица:</strong>
				{{user.streetName}}, {{user.streetNumber}}
			</p>
			<p>
				<strong class="user-detail-data__label">Почтовый индекс:</strong>
				{{user.postcode}}
			</p>
		</div>

		<div class="user-detail-data__group user-detail-data__contact">
			<p>
				<strong class="user-detail-data__label">Электронная почта:</strong>
				{{user.email}}
			</p>
			<p>
				<strong class="user-detail-data__label">Стационарный телефон:</strong>
				{{user.phone}}
			</p>
			<p>
				<strong class="user-detail-data__label">Мобильный телефон:</strong>
				{{user.cell}}
			</p>
		</div>

		<div class="user-detail-data__group">
			<p>
				<strong class="user-detail-data__label">Дата регистрации:</strong>
				{{user.registered}}
			</p>
		</div>
	</div>
</template>



<script>
	export default {
		props: {
			user: Object
		},
		data() {
			return {};
		},
		beforeCreate() {
			window.scroll({
				top: 0,
				left: 0
			});
		}
	};
</script>



<style lang="scss" scoped>
	.user-detail-data {
		max-width: 600px;
		margin: 0 auto;
		padding: 1rem;
		font-size: 1.5rem;
		background-color: #ececec;

		&__label {
			color: #c1b00f;
		}

		&__group {
			margin: 20px;
		}
	}
</style>
