<script lang="ts">
	import hankncrochet from './assets/counter-icons/hankncrochet.png';
	import hanknknit from './assets/counter-icons/hanknknit.png';
	import cake from './assets/counter-icons/cake.png';
	import mittens from './assets/counter-icons/mittens.png';
	import socks from './assets/counter-icons/socks.png';
	import sweater from './assets/counter-icons/sweater.png';

	interface Props {
		/** Which counter icon to display */
		icon: 'hankncrochet' | 'hanknknit' | 'cake' | 'mittens' | 'socks' | 'sweater';
		/** The onclick event handler */
		onclick?: () => void;
	}

	const { icon, onclick, ...props }: Props = $props();

	let iconInfo = $derived.by(() => {
		switch (icon) {
			case 'hankncrochet':
				return { src: hankncrochet, alt: 'Hank n Crochet' };
			case 'hanknknit':
				return { src: hanknknit, alt: 'Hank n Knit' };
			case 'cake':
				return { src: cake, alt: 'Cake' };
			case 'mittens':
				return { src: mittens, alt: 'Mittens' };
			case 'socks':
				return { src: socks, alt: 'Socks' };
			case 'sweater':
				return { src: sweater, alt: 'Sweater' };
		}
	});
</script>

<img
	src={iconInfo.src}
	alt={iconInfo.alt}
	class={['storybook-button', `storybook-button--${icon}`].join(' ')}
	{onclick}
	{...props}
/>
