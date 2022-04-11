<script>
	import { onMount } from 'svelte';
	import { push } from 'svelte-spa-router';
	import { fly } from 'svelte/transition';
	import Timer from '../Timer.svelte';

	let showListNum = Array.from(Array(30), (v, k) => k + 1);
	let gameOver = false;
	let gameClear = false;
	$: count = 1;

	const shuffleArray = ([...array]) => {

		for (let i = array.length - 1; i >= 0; i--) {
			const j = Math.floor(Math.random() * (i + 1));
			[array[i], array[j]] = [array[j], array[i]];
		}

		return array;
	}

	function increment(index) {

		if (count === showListNum[index]) {
			document.getElementById(index + 1).setAttribute("disabled", true);
			count++;

			if (count === 31) gameClear = true;
		}
		else {
			gameOver = true;
		}
	}

	onMount(() => {
		showListNum = shuffleArray(showListNum);
	})
</script>

<main>
	<h1 in:fly>{count}</h1>

	<div class="card">
		{#each showListNum as value, i}
			<button on:click="{() => {increment(i)}}" id="{i + 1}" disabled={gameOver || gameClear}>{showListNum[i]}</button>
			{#if (i + 1) % 5 === 0}
				<br>
			{/if}
		{/each}
	</div>

	<Timer {gameOver} {gameClear}></Timer>

	<div class="gameOver gameEnd">
		{#if gameOver}
			<h1 in:fly>GAME OVER</h1>	
		{/if}
	</div>

	<div class="gameClear gameEnd">
		{#if gameClear}
			<h1 in:fly>GAME CLEAR</h1>	
		{/if}
	</div>

    <button on:click={() => push('/')}>戻る</button>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin-top: 0em;
	}

	.gameEnd {
		text-transform: uppercase;
		font-size: 1em;
		font-weight: 100;
		margin-top: 0em;
	}

	.gameOver {
		color: #ff3e00;
	}

	.gameClear {
		color: #24c5ff;
	}

	.card button {
		margin: 1;
		width: 50px;
		height: 50px;
		border: 1px solid #68779a;
		background: #cbe8fa;
		cursor: pointer;
	}

	.card button:disabled {
		color: rgb(0, 0, 0);
    	background: #ff83c7;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>