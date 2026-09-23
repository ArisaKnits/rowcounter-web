<script module>
	import { defineMeta } from '@storybook/addon-svelte-csf';
	import RowCounterContentView from './RowCounterContentView.svelte';
	import { fn } from 'storybook/test';

	// More on how to set up stories at: https://storybook.js.org/docs/writing-stories
	const { Story } = defineMeta({
		title: 'Example/RowCounterContentView',
		component: RowCounterContentView,
		// This component will have an automatically generated Autodocs entry: https://storybook.js.org/docs/writing-docs/autodocs
		tags: ['autodocs'],
		parameters: {
			// More on how to position stories at: https://storybook.js.org/docs/configure/story-layout
			layout: 'fullscreen'
		},
		args: {
			onLogin: fn(),
			onLogout: fn(),
			onCreateAccount: fn()
		}
	});
</script>

<Story name="Logged In" args={{ rowCount: 5, repeatCount: 1 }} />

<Story name="Logged Out" args={{ rowCount: 37, repeatCount: 0 }} />

<Story name="Initial State" args={{ rowCount: 0, repeatCount: 0 }} />

