<script>
	import Router from 'svelte-spa-router'
	import Home from './Home.svelte';
	import Game1 from './components/game1/Game1.svelte'
	import Game2 from './components/game2/Game2.svelte'

	const routes = {
		'/': Home,
		'/game1': Game1,
		'/geme2': Game2,
		'*': Home
  	}
</script>

<Router routes={routes}/>