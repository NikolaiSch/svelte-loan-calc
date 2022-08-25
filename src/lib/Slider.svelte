<script lang="ts">
	export let name: string;
	export let range: [number, number];
	export let additionalSymbol = '';
	export let value = range[0];
</script>

<main>
	<div>
		<label
			><p>{name} - <input bind:value id="b" /> {additionalSymbol}</p>
			<input type="range" min={range[0]} max={range[1]} bind:value /></label
		>
	</div>
</main>

<style>
	div {
		padding: 30px;
		border-radius: 10px;
		border: 1px solid black;
		/* display: inline-block; */
		/* width: 300px; */
		margin: 10px;
	}

	#b {
		width: 30px;
		background-color: aquamarine;
		border: none;
		padding: 5px;
		border-radius: 5px;
	}
</style>
