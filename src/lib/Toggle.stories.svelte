<script>
	import { Meta, Template, Story } from '@storybook/addon-svelte-csf';
	import Toggle from './Toggle.svelte';
</script>

<Meta
	title="Sveltio/Toggle"
	component={Toggle}
	argTypes={{
		label: { control: 'text' },
		primary: { control: 'boolean' },
		backgroundColor: { control: 'color' },
		size: {
			control: { type: 'select', options: ['small', 'medium', 'large'] }
		},
		onClick: { action: 'onClick' }
	}}
/>

<Template let:args>
	<Toggle {...args} on:click={args.onClick} />
</Template>

<Story
	name="Labeled"
	args={{
		primary: true,
		label: 'Check me'
	}}
/>

<Story
	name="Blank"
	args={{
		label: ''
	}}
/>
