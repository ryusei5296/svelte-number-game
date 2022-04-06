<script>
	import StartGame from './components/home/StartGame.svelte';
	import InputName from './components/home/InputName.svelte';

	import { fly } from 'svelte/transition'

	// import Countdown from './Common/Countdown.svelte'

	const name = 'World';
	let done = false;
</script>
<link href="https://fonts.googleapis.com/css?family=Material+Icons|Material+Icons+Outlined|Material+Icons+Round|Material+Icons+Sharp|Material+Icons+Two+Tone" rel="stylesheet">

<main>
	<span class="material-icons-outlined">
		home
		</span>
	<h1>Hello {name}!</h1>
	<InputName buttonName={"Input your name"}/> <br>
	<StartGame />

	<div class="inner">
		<h1 class="margin-0">START！</h1>

		{#if done}
			<h2 in:fly>TIME UP!</h2>	
		{/if}	
	</div>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin-top: 0em;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
		margin-top: 0em;
	}

	.margin-0 {
		margin: 0em;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>