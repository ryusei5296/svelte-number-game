<script>
	import { push } from 'svelte-spa-router'
  import SelectButton from './SelectButton.svelte';

  function movePage(event) {
    push(`/${event.detail}`)
  }
</script>

<SelectButton on:notify="{movePage}"/>