<script>
    export let current = 'game1';
    export let gamemode;

  
</script>

<button class:selected = "{gamemode.mode === current}" on:click >{gamemode.buttonName}</button>

<style>
    button {
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
  }

  button:active {
    background-color: rgba(255, 62, 0, 0.2);
  }
    .selected {
        border-color: #ff3e00;
	}
</style>