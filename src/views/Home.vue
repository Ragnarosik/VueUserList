<template>
	<section class="home">
		<div class="logo-vue">
			<img src="../assets/logoPNG.png" />
		</div>
		<div class="definition">
			<p>
				Статистика по пользователям
			</p>
		</div>
		<template>
			<div style="margin: auto 600px; border-style: double; border-color: #3f3f3f; width: auto;" id="chart">
				<div>
					<div class="chart-wrap">
							<apexchart type="donut" width="350" :options="options" :series="series"></apexchart>
						</div>
					</div>

					<div class="actions">
						<button class="button"
								@click="count">{{'Подсчет'}}</button>
					</div>
				</div>
		</template>
	</section>
</template>



<script>
	import VueApexCharts from 'vue-apexcharts';
	export default {
		data: function() {
			return {
				options: {
					legend: {
						position: 'top'
					},
					labels: ['male', 'female'],
				},
				series: [/*this.users.gender*/0, 0]
			}
		},
		components: {
			apexchart: VueApexCharts,
		},
		props: {
			users: Array
		},
		methods: {
			count: function () {
				this.series = this.series.map(function() {
					return Math.floor(Math.random() * (15))
					//return this.series
				})
			},
		},
	};
</script>



<style lang="scss" scoped>
	.logo-vue {
		text-align: center;
	}
	.definition {
		text-align: center;
		color: #726452;
		font-family: "Times New Roman";
		font-size: 3em;
		font-weight: 300;
	}
	.button {
		background-color: whitesmoke;
		color: black;
		border: 2px solid #c1b00f;
		padding: 0 1rem;
		display: inline-block;
		height: 25px;
		line-height: 25px;
		margin-bottom: 3px;
		margin-left: 300px;
		font-size: medium;
		font-family: "Times New Roman";
	}
</style>
