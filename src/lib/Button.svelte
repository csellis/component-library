<script>
	import { createEventDispatcher } from 'svelte';

	export let primary = false;
	export let size = 'medium';
	export let label = '';

	const dispatch = createEventDispatcher();
	/**
	 * Button click handler
	 */
	function onClick(event) {
		dispatch('click', event);
	}
</script>

<button
	type="button"
	class={[
		'sveltio-button',
		`sveltio-button--${size}`,
		`sveltio-button--${primary ? 'primary' : 'secondary'}`
	].join(' ')}
	on:click={onClick}
>
	{label}
</button>

<style>
	.sveltio-button {
		font-family: 'Nunito Sans', 'Helvetica Neue', Helvetica, Arial, sans-serif;
		font-weight: 700;
		border: 0;
		border-radius: 3px;
		cursor: pointer;
		display: inline-block;
		line-height: 1;
	}
	.sveltio-button--primary {
		color: #1b116e;
		background-color: #6bedb5;
	}
	.sveltio-button--secondary {
		color: #ffffff;
		background-color: #1b116e;
		box-shadow: rgba(0, 0, 0, 0.15) 0px 0px 0px 1px inset;
	}
	.sveltio-button--small {
		font-size: 12px;
		padding: 10px 16px;
	}
	.sveltio-button--medium {
		font-size: 14px;
		padding: 11px 20px;
	}
	.sveltio-button--large {
		font-size: 16px;
		padding: 12px 24px;
	}

	.sveltio-button--primary :hover {
		color: #1b116e;
		background-color: #55bd90;
	}

	.sveltio-button--primary :active {
		color: #1b116e;
		background-color: #55bd90;
		border: solid 2px #1b116e;
	}

	.sveltio-button--primary :disabled {
		color: #1b116e;
		opacity: 0.5;
		background-color: #6bedb5;
	}

	.sveltio-button--secondary :hover {
		color: #1b116e;
		background-color: #55bd90;
	}

	.sveltio-button--secondary :active {
		color: #1b116e;
		background-color: #6bedb5;
		border: solid 2px #1b116e;
	}

	.sveltio-button--secondary :disabled {
		color: #ffffff;
		opacity: 0.5;
		background-color: #1b116e;
	}
</style>
