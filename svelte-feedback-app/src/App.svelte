<script>
	// export let name;
	let firstName = 'Natalie';
	let lastName = 'Kendrick';
	let color = 'blue';
	let showText = false;

	$: name = firstName + ' ' + lastName;

	const toggle = () => {
		color = color === 'goldenrod' ? color = 'red' : color = 'goldenrod';
		showText = !showText;
	};

</script>

<main>
	<h1 style="color: {color}">Hello {name}!</h1>

	{#if showText }

	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>

	{:else}
		<p>Ops</p>
	{/if}

	<button on:click={()=> color='goldenrod' }>Click</button>

	<button on:click={toggle}>Click More</button>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>