<script>
	import { createEventDispatcher } from 'svelte';

	export let placeholder = '';
	export let label = '';
	export let disabled = false;

	export let state = 'active';

	const dispatch = createEventDispatcher();

	/**
	 * input change handler
	 */
	function onChange(event) {
		dispatch('click', event);
	}
</script>

<label>
	{#if label}
		<span class="sveltio-input-label">{label}</span>
	{/if}

	<input
		{disabled}
		type="text"
		class={['sveltio-input', `sveltio-input--${state}`].join(' ')}
		{placeholder}
	/>
</label>

<style>
	.sveltio-input {
		font-family: 'Nunito Sans', 'Helvetica Neue', Helvetica, Arial, sans-serif;
		font-weight: 700;
		min-height: 25px;
		margin: 2px;
		border-radius: 3px;
		border: solid 2px #353637;
		background-color: #ffffff;
	}

	.sveltio-input ::focus {
		border: solid 2px #1b116e;
	}

	.sveltio-input--success {
		border: solid 2px #067d68;
	}

	.sveltio-input--error {
		border: solid 2px #a9150b;
	}

	.sveltio-input--disabled {
		color: #e4e3ea;
		border: solid 2px #e4e3ea;
	}

	.sveltio-input ::-webkit-input-placeholder {
		color: red;
	}

	.sveltio-input-label {
		font-family: 'Nunito Sans', 'Helvetica Neue', Helvetica, Arial, sans-serif;
		font-weight: 700;
	}
</style>
