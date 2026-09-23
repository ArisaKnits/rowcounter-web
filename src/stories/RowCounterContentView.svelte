<script lang="ts">
	import Yarn from '@lucide/svelte/icons/spool';
	import MinusIcon from '@lucide/svelte/icons/minus';
	import './app.css';
	import Button from './Button.svelte';

	interface Props {
		rowCount: number;
		repeatCount: number;
		onLogin?: () => void;
		onLogout?: () => void;
		onCreateAccount?: () => void;
	}

	const { rowCount, repeatCount, onLogin, onLogout, onCreateAccount }: Props = $props();
</script>

<section class="flex flex-col items-center gap-4">
	<Yarn size="48" />
	<button class="btn rounded-full flex items-center justify-center aspect-square h-auto">
		<span class="countdown font-mono text-6xl font-extralight">
			<span class="font-extralight" style="--value:{rowCount}; --digits: 1;" aria-live="polite" aria-label={rowCount.toString()}>{rowCount}</span>
		</span>
	</button>
	<button class="btn btn-circle btn-xs"><MinusIcon /></button>
	<p>Repeats: {repeatCount}</p>
</section>
