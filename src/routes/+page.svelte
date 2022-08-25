<script lang="ts">
	import Slider from '../lib/Slider.svelte';

	let interest = 10;
	let days = 10;
	let initial = 100;

	let dailyInterest = 0;
	$: dailyInterest = Math.E ** (Math.log(interest / 100 + 1) / 30);
</script>

<div>
	<h1>Kolya's Calculator</h1>
	<form>
		<Slider name="Monthly Interest" range={[1, 100]} additionalSymbol="%" bind:value={interest} />
		<Slider name="Days" range={[1, 60]} additionalSymbol=" days" bind:value={days} />
		<Slider name="Initial Amount" range={[1, 1000]} additionalSymbol="£" bind:value={initial} />
	</form>
	<main>
		<p>Total Amount - £{Math.round(dailyInterest ** days * initial)}</p>
		<p>
			Total Cost - £{Math.round(dailyInterest ** days * initial - initial)}
		</p>
		<p>
			Total Interest - {Math.floor(dailyInterest ** days * 100 - 100)}%
		</p>

		<p>
			Daily Interest - {Math.floor(10000 * Math.E ** (Math.log(interest / 100 + 1) / 30)) / 10000}%
		</p>
	</main>
</div>

<style>
	:root {
		background-color: gray;
	}
	div {
		display: grid;
		grid-template-columns: 1fr 1fr;
	}
	form {
		grid-column: 1;
		border: 1px solid black;
		border-radius: 10px;
		margin: 10px;
		padding: 20px;
		background-color: azure;
	}

	main {
		grid-column: 2;
		border: 1px solid black;
		border-radius: 10px;
		margin: 10px;
		padding: 20px;
		background-color: azure;
		font-size: x-large;
	}
	h1 {
		text-align: center;
		color: aliceblue;
	}
</style>
