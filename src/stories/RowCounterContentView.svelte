<script lang="ts">
	import Yarn from '@lucide/svelte/icons/spool';
	import MinusIcon from '@lucide/svelte/icons/minus';
	import './app.css';
	import Button from './Button.svelte';

	interface Props {
		user?: { name: string };
		onLogin?: () => void;
		onLogout?: () => void;
		onCreateAccount?: () => void;
	}

	const { user, onLogin, onLogout, onCreateAccount }: Props = $props();
</script>

<section class="flex flex-col items-center gap-4">
	<Yarn size="48" />
	<button class="btn rounded-full flex items-center justify-center aspect-square h-auto">
		<span class="countdown font-mono text-6xl font-extralight">
			<span style="--value:59; --digits: 1;" aria-live="polite" aria-label="59">59</span>
		</span>
	</button>
	<button class="btn btn-circle btn-xs"><MinusIcon /></button>
	<p>Repeats: 1</p>
</section>
