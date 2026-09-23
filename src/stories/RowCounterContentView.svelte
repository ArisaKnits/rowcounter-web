<script lang="ts">
	import MinusIcon from '@lucide/svelte/icons/minus';
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

<section
	class="flex flex-col items-center gap-4 text-white"
	style="--counter-color: var(--color-{bgColor}); background-color: var(--counter-color);"
>
	<CounterIcon {icon} class="h-10" />
	<button class="btn flex aspect-square h-auto items-center justify-center rounded-full">
		<span class="countdown font-mono text-6xl font-extralight">
			<span
				class="font-extralight"
				style="--value:{currentRow}; --digits: 1;"
				aria-live="polite"
				aria-label={currentRow.toString()}>{currentRow}</span
			>
		</span>
	</button>
	<button class="btn btn-circle btn-xs"><MinusIcon /></button>
	<p>Repeats: {repeatCount}</p>
</section>

<style>
	button {
		color: white;
		background-color: color-mix(in srgb, var(--counter-color) 75%, white);
	}
	button:has(.countdown) {
		corner-shape: squircle;
	}
</style>
