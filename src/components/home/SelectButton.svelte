<script >
  import Button from './Button.svelte'

  import { createEventDispatcher } from 'svelte'

  export let current = 'game1'

  const dispatch = createEventDispatcher()
  const gameModeList = [
    {id: 1 ,mode: 'game1', buttonName: "1~30"},
    {id: 2, mode: 'geme2', buttonName: "A~Z"},
    {id: 3, mode: 'lowerAlphabet', buttonName: "a~z"}
  ]
  const radioSelect = (gamemode) => {
    current = gamemode
  }
</script>

{#each gameModeList as gamemode}
  <Button {gamemode} {current} on:click={() => {radioSelect(gamemode.mode)}}></Button>
{/each}

<br>
<button class="start" on:click="{() => dispatch('notify', current)}">START!</button>

<style>
  .start {
      font-family: inherit;
      font-size: inherit;
      padding: 1em 2em;
      color: #ff3e00;
      background-color: rgba(255, 62, 0, 0.1);
      border-radius: 2em;
      border: 2px solid rgba(255, 62, 0, 0);
      outline: none;
      width: 200px;
      font-variant-numeric: tabular-nums;
      cursor: pointer;
      color: #ff0000;
      background-color: rgba(255, 136, 171, 0.1);
      border-radius: 1em;
      width: 600px;
  }

  button:active {
    background-color: rgba(255, 62, 0, 0.2);
  }
</style>