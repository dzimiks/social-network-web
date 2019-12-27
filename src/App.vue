<template>
	<div id="app">
		<MainView></MainView>
	</div>
</template>

<script>
	import MainView from './components/MainView.vue';

	export default {
		name: 'app',
		components: {
			MainView
		}
	}
</script>

<style>
	.card {
		margin: 2rem 0;
		border: 0;
		box-shadow: 0 1px 3px rgba(0, 0, 0, 0.12), 0 1px 2px rgba(0, 0, 0, 0.24);
	}

	.card-header-text {
		padding: .75rem 1.25rem;
		background: linear-gradient(to right, #b92b27, #1565c0);
		color: white;
		border-top-right-radius: .25rem;
		border-top-left-radius: .25rem;
	}
</style>
