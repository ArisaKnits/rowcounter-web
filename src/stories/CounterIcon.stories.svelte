<script module>
	import { defineMeta } from '@storybook/addon-svelte-csf';
	import CounterIcon from './CounterIcon.svelte';
	import { fn } from 'storybook/test';

	// More on how to set up stories at: https://storybook.js.org/docs/writing-stories
	const { Story } = defineMeta({
		title: 'Example/CounterIcon',
		component: CounterIcon,
		globals: {
			backgrounds: { value: 'dark'}
		},
		tags: ['autodocs'],
		argTypes: {
			icon: {
				control: { type: 'select' },
				options: ['hankncrochet', 'hanknknit', 'cake', 'mittens', 'socks', 'sweater']
			}
		},
		args: {
			onclick: fn()
		}
	});
</script>

<!-- More on writing stories with args: https://storybook.js.org/docs/writing-stories/args -->
<Story name="Hank'n'Crochet" args={{ icon: 'hankncrochet' }} />

<Story name="Hank'n'Knit" args={{ icon: 'hanknknit' }} />

<Story name="Cake" args={{ icon: 'cake' }} />

<Story name="Mittens" args={{ icon: 'mittens' }} />

<Story name="Socks" args={{ icon: 'socks' }} />

<Story name="Sweater" args={{ icon: 'sweater' }} />
