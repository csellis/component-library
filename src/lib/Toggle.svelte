<script lang="ts">
	export let label = '';
	export let isToggled = false;
	export let style = '';
</script>

<label {style} class="sveltio-toggle-label">
	<input type="checkbox" class="sveltio-input" bind:checked={isToggled} />
	<div class="sveltio-toggle" />
	{label}
</label>

<style>
	.sveltio-toggle-label {
		--width: 40px;
		--height: calc(var(--width) / 2);
		--radius: calc(var(--height) / 2);
		display: flex;
	}

	.sveltio-toggle {
		position: relative;
		width: var(--width);
		height: var(--height);
		border-radius: var(--radius);
		border: solid 1px #c2c2c3;
		transition: background-color 0.3s ease;
		margin-right: 5px;
		background-color: var(--toggleBackgroundColor, #c2c2c3);
	}

	.sveltio-toggle::after {
		content: '';
		position: absolute;
		top: -1px;
		left: -1px;
		height: var(--height);
		width: var(--height);
		border-radius: var(--radius);
		background-color: var(--toggleButtonColor, #ffffff);
		box-shadow: 2px 4px 6px rgba(0, 0, 0, 0.3);
		transition: transform 0.3s ease;
	}
	.sveltio-input {
		display: none;
	}

	.sveltio-input:checked + .toggle {
		background-color: var(--toggleCheckedBackgroundColor, #1b116e);
	}

	.sveltio-input:checked + .toggle::after {
		transform: translate3d(100%, 0, 0);
	}
</style>
