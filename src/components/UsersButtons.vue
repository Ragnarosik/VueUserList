<template>
	<div class="users-buttons">
		<button @click="setShowEmit" class="users-buttons__item" :disabled="false">{{'Скрыть информацию'}}</button>
		<button @click="setRandomEmit" class="users-buttons__item">{{'Перемешать'}}</button>
	</div>
</template>


<script>
	export default {
		methods: {
			setShowEmit() {
				this.$emit("show");
			},
			setRandomEmit() {
				this.$emit("random");
			}
		},
	};
</script>


<style lang="scss" scoped>
	.users-buttons {
		width: 100%;
		padding: 1rem;
		display: flex;
		justify-content: center;
		align-items: center;
		position: fixed;
		bottom: 0;
		left: 0;
		z-index: 999;
		background-color: #c1b00f;
		box-shadow: 0 0 1rem 0.5rem rgba(0, 0, 0, 0.3);

		&__item {
			padding: 1rem;
			font-weight: 600;
			font-size: 0.8rem;
			color: #726452;
			border: none;
			background-color: #ececec;
			cursor: pointer;

			&:not(:last-child) {
				margin-right: 1rem;
			}

			&:hover {
				color: #ececec;
				background-color: #726452;
			}
		}
	}
</style>

