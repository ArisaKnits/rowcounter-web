<script lang="ts">
	import './app.css';
	import CounterIcon from './CounterIcon.svelte';

	interface Props {
		/** The number of the current row the user is on (1-based index) */
		currentRow: number;
		/** The row after which the pattern repeats */
		repeatAfterRow: number;

		/** The number of times the pattern has repeated */
		repeatCount: number;
		/** Which counter icon to display */
		icon: 'hankncrochet' | 'hanknknit' | 'cake' | 'mittens' | 'socks' | 'sweater';
		/** The background color for the counter */
		bgColor: 'black' | 'blush' | 'dandelion' | 'darkblue' | 'darkteal' | 'magenta' | 'sky';
		onLogin?: () => void;
		onLogout?: () => void;
		onCreateAccount?: () => void;
	}

	const {
		currentRow,
		repeatAfterRow = 0,
		repeatCount = 0,
		icon,
		bgColor,
		onLogin,
		onLogout,
		onCreateAccount
	}: Props = $props();
</script>

<div
	class="flex max-h-32 max-w-sm items-center justify-around gap-4 rounded-full p-4 text-white"
	style="--counter-color: var(--color-{bgColor}); background-color: var(--counter-color);"
>
	<CounterIcon {icon} class="max-h-full min-h-10" />
	<div class="flex flex-col items-center">
		<span class="font-mono text-4xl font-extralight">
			{currentRow}
		</span>
		<p class="text-sm">Repeats: {repeatCount}</p>
	</div>
</div>
