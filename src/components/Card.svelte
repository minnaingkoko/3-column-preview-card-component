<script lang="ts">
	export let color: string,
		icon: string,
		heading: string,
		text: string,
		tl: string,
		tr: string,
		bl: string,
		br: string;

	let Color = false;
	let toggleColor = () => {
		Color = !Color;
	};
</script>

<div
	class="card"
	style="background-color: {color}; border-top-left-radius: {tl}px; border-top-right-radius: {tr}px; border-bottom-left-radius: {bl}px; border-bottom-right-radius: {br}px;"
>
	<div class="info">
		<img src="/images/{icon}" alt="" />
		<h1 class="heading">{heading}</h1>
		<p class="text">{text}</p>
	</div>
	<div
		class="btn"
		on:mouseenter={toggleColor}
		on:mouseleave={toggleColor}
		style="color: {Color ? '#ffffff' : color}; background-color: {Color
			? color
			: '#f2f2f2'}; border: 2px solid {Color ? '#f2f2f2' : color}"
	>
		Learn more
	</div>
</div>

<style>
	.card {
		@apply w-[300px] h-[500px] p-[42px] flex flex-col justify-between;
	}
	.heading {
		@apply text-[#f2f2f2] mt-[32px] font-['BigShouldersDisplay'] font-bold text-[32px];
	}
	.text {
		@apply mt-[24px] text-[15px];
		color: hsla(0, 0%, 100%, 0.75);
	}
	.btn {
		@apply w-[145px] h-[45px] rounded-[24px] flex justify-center items-center cursor-pointer text-[16px] duration-300;
	}
	@media only screen and (max-width: 900px) {
		.card {
			width: 250px;
		}
	}
	@media only screen and (max-width: 750px) {
		.card {
			width: 300px;
			height: 400px;
		}
	}
</style>
