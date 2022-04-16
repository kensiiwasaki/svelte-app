<script lang="ts">
	let x = [0, 0];
	let all = 0;
	let name = ["", ""];

	function plus(i) {
		console.log(i);
		
		x[i] = x[i] + 1
	}

	function minus(i) {
		x[i] = x[i] - 1
	}

	function reset(i) {
		x[i] = 0
	}

	$: totala = x[0];
	$: totalb = x[1];
	$: allTotal = totala + totalb;
</script>

<div>
	<main><h1>Multiple Counter</h1></main>
</div>

<main>
	<input  bind:value={name[0]}>
	{totala}
	<button on:click={() => plus(0)}>
		+
	</button>
	<button on:click={() => minus(0)}>
		-
	</button>
	<button on:click={() => reset(0)}>
		0
	</button>
</main>
<main>
	<input  bind:value={name[1]}>
	{totalb}
	<button on:click={() => plus(1)}>
		+
	</button>
	<button on:click={() => minus(1)}>
		-
	</button>
	<button on:click={() => reset(1)}>
		0
	</button>
</main>

<main>
	<p>All: {allTotal}</p>
	<p>list title : {name[0]},{name[1]}</p>	
</main>


<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>