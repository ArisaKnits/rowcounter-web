<script module>
	import { defineMeta } from '@storybook/addon-svelte-csf';
	import RowCounterListItem from './RowCounterListItem.svelte';
	import { fn } from 'storybook/test';

	// More on how to set up stories at: https://storybook.js.org/docs/writing-stories
	const { Story } = defineMeta({
		title: 'Example/RowCounterListItem',
		component: RowCounterListItem,
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

<Story
	name="Default"
	args={{ id: 1, currentRow: 5, repeatCount: 1, icon: 'hankncrochet', bgColor: 'magenta' }}
/>

<Story
	name="Example 1"
	args={{ id: 2, currentRow: 37, repeatCount: 0, icon: 'mittens', bgColor: 'darkblue' }}
/>

<Story
	name="Initial State"
	args={{ id: 3, currentRow: 0, repeatCount: 0, icon: 'cake', bgColor: 'darkteal' }}
/>
