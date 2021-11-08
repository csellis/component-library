<script>
	import { Meta, Template, Story } from '@storybook/addon-svelte-csf';
	import Input from './Input.svelte';
</script>

<Meta
	title="Sveltio/Input"
	component={Input}
	argTypes={{
		backgroundColor: { control: 'color' },
		state: {
			control: { type: 'select', options: ['active', 'success', 'error'] }
		},
		onChange: { action: 'onChange' },
		disabled: { control: 'boolean' }
	}}
/>

<Template let:args>
	<Input {...args} on:change={args.onChange} />
</Template>

<Story
	name="Active"
	args={{
		placeholder: 'Text Input Active',
		state: 'active'
	}}
/>

<Story
	name="Success"
	args={{
		placeholder: 'Text Input Success',
		state: 'success'
	}}
/>
<Story
	name="Error"
	args={{
		placeholder: 'Text Input Error',
		state: 'error'
	}}
/>

<Story
	name="Disabled"
	args={{
		state: 'disabled',
		disabled: true
	}}
/>
