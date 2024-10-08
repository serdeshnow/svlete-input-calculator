<script lang="ts">
	import ControlPanel from '$lib/components/ControlPanel.svelte';
	import InfoPanel from '$lib/components/InfoPanel.svelte';
	import Image from '$lib/components/Image.svelte';

	let output = 0;
</script>

<article class="calculator">
	<Image/>
	<ControlPanel bind:output />
	<InfoPanel {output} />
</article>

<style lang="scss">
	.calculator {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		gap: var(--spacing-md);
		min-height: 100vh;
	}
</style>
