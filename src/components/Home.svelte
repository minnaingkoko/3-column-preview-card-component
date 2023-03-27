<script>
	import ColumnCards from './ColumnCards.svelte';
	import MediaQuery from './MediaQuery.svelte';
	import RowCards from './RowCards.svelte';
</script>

<main class="home">
	<div class="wrapper">
		<MediaQuery query="(max-width: 750px)" let:matches>
			{#if matches}
				<RowCards />
			{:else}
				<ColumnCards />
			{/if}
		</MediaQuery>
	</div>
</main>

<style>
	.home {
		@apply w-[100vw] h-[100vh] flex bg-[#f2f2f2] justify-center items-center;
	}
	.wrapper {
		@apply w-[900px] h-[500px] rounded-[10px] flex flex-row;
	}
	@media only screen and (max-width: 900px) {
		.wrapper {
			width: 750px;
		}
	}
	@media only screen and (max-width: 750px) {
		.home {
			width: 100%;
			height: 100%;
		}
		.wrapper {
			margin-top: 48px;
			margin-bottom: 48px;
			flex-direction: column;
			width: 300px;
			height: 1200px;
		}
	}
</style>
