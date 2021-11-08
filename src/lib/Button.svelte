<script>
	import { createEventDispatcher } from 'svelte';

	export let primary = false;
	export let size = 'medium';
	export let label = '';
	export let classes = 'bg-blue-500';

	const dispatch = createEventDispatcher();
	/**
	 * Button click handler
	 */
	function onClick(event) {
		dispatch('click', event);
	}
</script>

<button type="button" class={classes} on:click={onClick}>
	{label}
</button>
